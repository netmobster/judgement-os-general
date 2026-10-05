---
name: boot
description: "A phased start to the day: a short brief, FOR CC reminders, one pick (style and energy), then one phase at a time, each skippable. Run it when the user says boot, boot up or morning, or types /day:boot."
argument-hint: "[bare|project|general]"
---

# /boot: a phased start to the day

**Why it's shaped like this.** A morning start that shows everything at once gets skipped. This
one is a brief, not a menu: **Claude decides what matters, the user picks only the style**, and
everything else arrives one piece at a time and can be skipped.

Run it when the user says "boot", "boot up" or "morning", or types `/day:boot`. **Not** on every
session's first message.

**Today's state** is `day.json` in the state folder (the settings' `stateDir`). Change it **only
through** `node "${CLAUDE_PLUGIN_ROOT}/scripts/day.js" <cmd>`, never by hand: another session may
be writing it too. When the session has a name, pass `--by <name>` on every write.

## The display rule: what the user must read ends the turn

The app collapses text written before a tool call into a one-line summary. Only the text after a
turn's last tool call reaches the user in full. So:
- **Run every tool call first**, then write the content as the turn's final text.
- **Never follow must-read text with a tool call in the same turn.** If a picker has to come after
  content, it waits for the user's next message.
- A picker's own question text is safe: keep what the choice depends on inside the question.

## 1. Silent pre-step: no output

1. `node "${CLAUDE_PLUGIN_ROOT}/scripts/day.js" show` → today's state, in the settings' time zone.
   If `style` is already set, a boot already ran today: say so in one line and offer the held
   items instead of booting again.
2. **The tasks.**
   Read the project's `TASKS.md` (the settings' `tasks` names the file). Read it the way the user
   writes it: open checklist items, any section called Now, Today, Doing or Next first, and any
   date that says when something is due. **No TASKS.md:** the brief works from the handoff alone,
   and the turn says once that a `TASKS.md` gives it more to work from.
   **Private task contexts never appear** (the settings' `privateTopics.taskContexts`), and
   neither does a task whose title carries a private word.
3. **The handoff.**
   If the project keeps one (a `HANDOFF.md`, or the newest entry in its session notes), its next
   steps and open loops.

## 2. Turn 1: the brief and the reminders

After the pre-step's tool calls, the final text is the brief, then the reminders (if any), then
one line, and **the turn ends.** No picker in this turn (display rule). The line: *"Ready? Style
and energy next."*

### The brief: three lines, at most

```
{Day} {d} {Mon}
{the thing that matters most today}
{the second thing, if there is one}
```

Lines 2–3 are **Claude's pick**, in plain words, from: something due today that matters · a
blocker or an at-risk item in the handoff · the handoff's first next step · items held from
yesterday (`from: "yesterday"` in day.json).

- **Every number carries its action.** "The release notes are due today: finish the changes
  list", never "1 task due today".
- **No overdue count, no totals.** Counts with no action attached are guilt scores. Task review
  happens at the mid-day check-in, when there's momentum to spend on it.
- Fewer lines is fine. One line is fine.

### Reminders for Claude

A task whose title **starts** with `FOR CC` or `ASSIGN CC` (any case, followed by `:`, `-` or
`—`), or carries the marker in capitals anywhere, is the user saying *"remind me at boot."* They
show under the brief at every boot, one line each with the marker stripped, until they're done
or dropped. **Not:** lowercase prose ("ask for CC access"). No matches: no block at all.

## 3. Turn 2: style and energy

On the user's next message after turn 1, whatever it says. If it already names a style and/or
energy ("general 7", "bare"), take them and skip the picker (or ask only for what's missing).
Otherwise one `AskUserQuestion` call, two questions:

1. **Style?** `bare` · `project` · `general` (described from the table below).
2. **Energy?** `1–3 low` · `4–5` · `6–7` · `8–10`. A typed number wins; otherwise store the
   midpoint (2, 4.5, 6.5, 9).

A dismissed style is `bare`; a dismissed energy is unknown (`-`). Then:
`node "${CLAUDE_PLUGIN_ROOT}/scripts/day.js" boot <style> <energy|-> <session name|->`

**Energy is acted on, never discussed.** Low means shorter responses, fewer options, one thing at
a time.

## 4. Styles

| style | what it is | phases, in order |
|---|---|---|
| `bare` | Just the brief. Straight to work. | none |
| `project` | Heads-down on one project. | `project` → `handoff` |
| `general` | A normal day. | `handoff` → `project` |

A style is picked fresh every boot. Nothing loads because it loaded yesterday.

## 5. Running a phase

**One phase per turn: offer → load → content last.** Offer it with one `AskUserQuestion`
question, "Next: {phase}: {one line on what it is}" → `load` · `skip` · `stop here`, at the
**start** of a turn, never after content.

- **load** → its tool calls, then its content as the turn's final text. Then **stop and wait**:
  the user's next message closes the phase.
- **skip** → `day.js hold <phase>`, and offer the next phase straight away.
- **stop here** → `day.js hold <this phase> <every remaining phase>`; the final text says
  "Held: {list}. They come back at mid-day."
- **Dismissed** → same as skip.

| phase | what it loads |
|---|---|
| `handoff` | The last session's next steps and open loops: the first three of each, `more` for the rest. Say where they came from. |
| `project` | The top of the project's board: what's next and what's blocked. Not the whole board. |

## Picker answers

`[No preference]` means dismissed: nothing, never a choice. A blank `Other` is also nothing.
Text typed into `Other` is a request: do what it names, or ask once if it names nothing.
