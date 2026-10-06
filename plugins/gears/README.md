# gears

Thinking tools: gears, loops and modes. Part of [Judgement OS](https://unstuck-games.com/judgement-os/), the General Edition: a second opinion for your Claude Code skills, only when they need one. (*Not an operating system.*)

## What it does

One router over 28 thinking tools built by Jay Wright: gears (scout, grumpy, closer, foundry, portrait and more), loops that chain them (forge, root-cause, retro, pattern, read and more) and modes (goofy, night, rest). Say what you need in plain words and it picks one. Add your own gears beside your settings.

## Install

In Claude Code:

```
/plugin marketplace add netmobster/judgement-os-general
/plugin install gears@judgement-os
```

The other seven plugins are in the same marketplace; [the README](https://github.com/netmobster/judgement-os-general) lists them all.

## Use it

| What | Does |
|---|---|
| the router | Plain words: "scout this", "grumpy on this", "root-cause it", "night mode". |
| `/gears:gear` | Run one by name; bare lists the menu. |

## Examples

```
what am I missing in this plan
/gears:gear forge
```

## What it needs

Nothing. Gears that lean on what they know about you read your /labs:profile file if there is one.

## Licence

MIT. Made by Jay Wright. [The Judgement OS page](https://unstuck-games.com/judgement-os/) has the whole story.
