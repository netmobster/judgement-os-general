# Judgement OS: General Edition 0.2.0

Built 2026-10-06 from source 992c4b9.

The General Edition works from files on your machine: a profile you write for yourself (/labs:profile starts it) and a TASKS.md for your day. It never needs an account.

## What is in it

| Plugin | Version | What it does |
|---|---|---|
| `labs` | 0.8.0 | The Judgement OS core: two judges consulted at marked decisions inside skills, the recorder that checks every answer and combines the two, the append-only log, /labs:profile, the one file the judges read about you, and /labs:try, which puts both judges on a morning blind so you can see which one you trust. |
| `guard` | 0.2.1 | Hard rules as hooks: deploys are printed for you to run, destructive commands and secrets ask first, state files change only through their scripts, and a session is archived only when you say so. |
| `sexyhtml` | 0.15.1 | House styles for finished HTML pages. /sexyhtml picks the style (ECHO-JAY by default, Seren for games) and the shape, with the Judgement OS weighing in when a request reads two ways; or name one: /sexyhtml:jay, /sexyhtml:seren, /sexyhtml:judgement-os. |
| `make` | 0.8.0 | Say what you want made, and it lands in the right place, in your look: a page, a form or card in the chat, a deck, a design, a living doc, a file or a design system. /make picks where it lands, with the Judgement OS weighing in when a request reads two ways, then hands it to the right maker. Pages go to sexyhtml. |
| `comms` | 0.6.0 | The send gate, which stops every outbound message until you type send; humanify, a de-tic pass for drafts written with AI in the room; and poll, which reads the Slack channels you choose and drafts replies that post only when you approve them. |
| `day` | 0.3.0 | A day loop for Claude Code: a short boot with the judges on the style pick, mid-day and end-of-day check-ins from your TASKS.md, habits you set up once, a daily reading and a phrase in a language you're learning, /flag for work you want to come back to, and a clock on every message. |
| `dice` | 0.2.0 | Real dice for tabletop games: any notation, advantage and disadvantage, damage, ability scores, never an invented roll. And nine party games to play with Claude: /dice:play. |
| `gears` | 0.3.0 | Thinking tools built by Jay Wright: gears, loops and modes through one router, or by name with /gears:gear. Add your own beside your profile. selfActual users get more, working from their live profile: see selfactual.ai. |

## Changes

What's new:

- **Habits.** `/day:habits` sets up your daily rows once, then scores them any time of day. Boot offers them until they're logged, and the check-ins bring back only the rows still open.
- **A daily reading and a language phrase.** `/day:daily` sets up either one. Boot shows the reading first and the phrase last; the reading moves on by itself each day, and the phrase waits until it lands.
- **The judges in `/day:boot`.** When the morning reads two ways, both judges weigh in on the style pick. When they agree with the rule, you hear nothing.
- **`/labs:try`.** Put both judges on a morning, blind, and pick the better answer before you learn which model wrote it.
- **Poll.** `/comms:poll` reads the Slack channels you choose, says what's new, and drafts replies that post only when you approve them.
- **Party games.** `/dice:play` and nine games to play with Claude.
- **More gears.** 28 on the menu, up from 19: foundry, prioritize-me and portrait, and the loops debrief, localize, patch, pattern, read and reformat, with the loop parts they use.
- **Two guides.** `/day:guide` walks you through trying each part once, and `/make:guide` through each make tool. Each is your own page, and it keeps your answers.
