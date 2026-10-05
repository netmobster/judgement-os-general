# Judgement OS: General Edition 0.1.0

Built 2026-10-05 from source e575aae.

The General Edition works from files on your machine: a profile you write for yourself (/labs:profile starts it) and a TASKS.md for your day. It never needs an account.

## What is in it

| Plugin | Version | What it does |
|---|---|---|
| `labs` | 0.7.2 | The Judgement OS core: two judges consulted at marked decisions inside skills, the recorder that checks every answer and combines the two, the append-only log, and /labs:profile, the one file the judges read about you. |
| `guard` | 0.2.1 | Hard rules as hooks: deploys are printed for you to run, destructive commands and secrets ask first, state files change only through their scripts, and a session is archived only when you say so. |
| `sexyhtml` | 0.15.0 | House styles for finished HTML pages. /sexyhtml picks the style (ECHO-JAY by default, Seren for games) and the shape, with the Judgement OS weighing in when a request reads two ways; or name one: /sexyhtml:jay, /sexyhtml:seren, /sexyhtml:judgement-os. |
| `make` | 0.7.2 | Say what you want made, and it lands in the right place, in your look: a page, a form or card in the chat, a deck, a design, a living doc, a file or a design system. /make picks where it lands, with the Judgement OS weighing in when a request reads two ways, then hands it to the right maker. Pages go to sexyhtml. |
| `comms` | 0.5.1 | The send gate, which stops every outbound message until you type send, and humanify, a de-tic pass for drafts written with AI in the room. |
| `day` | 0.2.1 | A day loop for Claude Code: a short boot and mid-day and end-of-day check-ins from your TASKS.md, /flag for work you want to come back to, and a clock on every message. |
| `dice` | 0.1.2 | Real dice for tabletop games: any notation, advantage and disadvantage, damage, ability scores. Never an invented roll. |
| `gears` | 0.2.3 | Thinking tools built by Jay Wright: gears, loops and modes through one router, or by name with /gears:gear. Add your own beside your profile. selfActual users get more, working from their live profile: see selfactual.ai. |

## Changes

First release.
