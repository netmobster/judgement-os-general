# The gears

**Built by Jay Wright.** selfActual users get more gears, working from their live profile: see selfactual.ai.

A **gear** is one way of thinking, in one Markdown file: SCOUT finds what's missing, GRUMPY
deflates, CLOSER lands it. A **loop** chains gears into stages: FORGE runs WHITEBOARD, then
DEVIL'S ADVOCATE, and keeps the part that survived. A **mode** changes the register, never the work.

| Folder | What ships |
|---|---|
| `gears/` | brief, closer, devils-advocate, grumpy, handoff, pressure-test, scout, whiteboard, and `thread` (a loop part) |
| `loops/` | architect, forge, gauntlet, locate, reality-check, retro, root-cause, scaffold |
| `modes/` | goofy-mode, night-mode, rest-mode |

Ask in plain words ("grumpy on this", "forge the pricing idea") and the router picks. By name:
`/gears:gear forge`. Bare `/gears:gear` lists them all.

## Write your own

Put it in the `gears/` folder beside your settings: `~/.claude/judgement-os/gears/<slug>.md` (on
Windows, `C:\Users\<you>\.claude\judgement-os\gears\`). The router reads that folder first, so
yours win on a name clash. No install, no build: the next request can use it.

```markdown
---
gear: hunch
title: HUNCH
category: Core
summary: One sentence: what it does, and when it earns its place.
trigger: '"hunch this" / "what does my gut say"'
---

# HUNCH

What it does, in two or three sentences.

## When it fires

The words or the moment that call for it.

## How to run

1. The first thing it does.
2. The next.

## Exit

How it ends, and what it hands back.
```

- **One job per gear.** If it does two things, it's two gears, or a loop.
- **A loop names its stages** by slug, in order (`whiteboard` → `devils-advocate` → `closer`), and
  says when it stops. Name the file `loop-<slug>.md` and set `category: Loop`.
- **A mode** is `<slug>-mode.md` with `category: Tonal/Mode`. It changes how things are said, never
  what gets done.
- **Say how it exits.** A gear that never ends is a mood.
- **Lean on the profile where it helps** (the one `/labs:profile` sets up), never on anything that
  needs an account.

Then ask for it: "hunch this", or `/gears:gear hunch`.
