# day

A day loop for Claude Code. Part of [Judgement OS](https://unstuck-games.com/judgement-os/), the General Edition: a second opinion for your Claude Code skills, only when they need one. (*Not an operating system.*)

## What it does

A short boot from your TASKS.md (the judges weigh in on its style when the morning reads two ways), mid-day and end-of-day check-ins, habits you set up once, a daily reading and a phrase in a language you're learning, and /flag for work you want to come back to. A clock on every message says when a check-in is due, and the first session after you install opens the field guide.

## Install

In Claude Code:

```
/plugin marketplace add netmobster/judgement-os-general
/plugin install day@judgement-os
```

The other seven plugins are in the same marketplace; [the README](https://github.com/netmobster/judgement-os-general) lists them all.

## Use it

| What | Does |
|---|---|
| `/day:boot` | A brief, one pick for the day's style and your energy, then one phase at a time. |
| `/day:checkin` | Mid-day or end of day: held items, open habits, tasks. |
| `/day:habits` | Your daily rows, set up once; score them any time. Never a score out of anything. |
| `/day:daily` | A daily reading and a language phrase, picked at setup. |
| `/day:flag` | When the work finishes, end with one question and push one line to your phone. |
| `/day:guide` | The field guide: one step per part, as your own page. |

## Examples

```
boot
/day:habits
/day:daily
```

## What it needs

A TASKS.md in your project for the brief and the check-ins. Everything else lives in ~/.claude/judgement-os/.

## Licence

MIT. Made by Jay Wright. [The Judgement OS page](https://unstuck-games.com/judgement-os/) has the whole story.
