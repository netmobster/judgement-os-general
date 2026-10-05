---
name: checkin
description: "A check-in, mid-day or end-of-day: held items, then tasks; at the end of the day, what carries to tomorrow. Claude offers it when the clock hook says it's due."
argument-hint: midday|eod
---

# /checkin: mid-day and end-of-day

**Why it exists.** Boot is a brief and a style pick. Whatever was skipped there is **held, not
lost**: it comes back here, when there's momentum to spend on it.

Today's state is `day.json` in the state folder. **Change it only through**
`node "${CLAUDE_PLUGIN_ROOT}/scripts/day.js" <cmd>`, never by hand.

## When it runs

The clock hook stamps every message with the time (the settings' time zone) and adds
`MID-DAY CHECK-IN DUE` after 13:00 or `END-OF-DAY CHECK-IN DUE` after 16:00, until that check-in
is done, skipped or snoozed. When it says one is due:

1. **Answer what the user actually asked first.** The check-in never jumps the queue.
2. Then **one line, plain prose** (a picker would swap out their input mid-work):
   *"Mid-day check-in: now, later, or not today?"* (or End-of-day).
3. **As you offer, run** `day.js offer <midday|eod>`: it goes quiet for an hour in every
   session. No answer counts as "later".
4. **now** → run it (below). **later** → nothing more. **not today** → `day.js skip <kind>`.

The user can also say "check-in", "mid-day" or "eod" at any time: run it directly. It's once a
day across all sessions, because day.json is the shared record.

**Display rule (from `/boot`):** pickers and writes first; what the user must read is the final
text. Each task question carries its own content (the title, how overdue) inside the question.

## Mid-day

1. **Held items.** `day.js show` → `held`. If any, one `AskUserQuestion` question, multiSelect:
   "Held from this morning: load any?" (at most four options; `from: "yesterday"` items say so).
   Chosen items run as boot phases, one per turn, and `day.js unhold <item>` once loaded.
2. **Task review.** The overdue and due-today tasks,
   from `TASKS.md`. **Three oldest overdue**, then anything due today, as `AskUserQuestion`
   questions, **one per task, at most four per call**, with how overdue it is in each question.
   Options: `done` · `tomorrow` · `next week` · `drop` → tick it · date it tomorrow · date it a
   week from today · remove it (or move it to a Dropped section, if the file has one).
   *(Today+1, not due+1: pushing a nine-day-old task to its own due+1 leaves it overdue.)*
   **Dismissed = skip:** write nothing; it comes back next time. **Private task contexts are left
   out** (the settings' `privateTopics.taskContexts`).
3. `day.js done midday`.

## End of day

1. **Tasks still due today**, most important first, with the same shape and verbs as mid-day.
   If mid-day never ran today, include the three oldest overdue too. Say it once: "N left for
   today". No percentages, no lecture. If the user waves it off, don't raise it again.
2. **Held items still open.** One question per item (at most four per call): `keep for
   tomorrow` · `let go`. Keep → `day.js carry <item>` (it becomes tomorrow's held item, marked
   from yesterday). Let go or dismissed → nothing. **Nothing carries unless it was kept on
   purpose.**
3. `day.js done eod`. The end of the day isn't the end of the session: close nothing unasked.

## Picker answers

`[No preference]` means dismissed: nothing, never a choice. A blank `Other` is also nothing.
Text typed into `Other` is a request: do what it names, or ask once.
