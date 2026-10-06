# dice

Real dice and party games. Part of [Judgement OS](https://unstuck-games.com/judgement-os/), the General Edition: a second opinion for your Claude Code skills, only when they need one. (*Not an operating system.*)

## What it does

Real dice for tabletop games, rolled by a script so the result is never made up: any notation, advantage and disadvantage, damage, ability scores. And nine party games to play with Claude, sharper with your profile and fine without it.

## Install

In Claude Code:

```
/plugin marketplace add netmobster/judgement-os-general
/plugin install dice@judgement-os
```

The other seven plugins are in the same marketplace; [the README](https://github.com/netmobster/judgement-os-general) lists them all.

## Use it

| What | Does |
|---|---|
| `/dice:roll` | Any dice notation: 1d20+5, 2d20kh1, 4d6dl1. |
| `/dice:play` | Would You Rather, Two Truths, Desert Island, Mad Libs, Story Chain and four more. |

## Examples

```
/dice:roll 2d20kh1+3
let's play would you rather
```

## What it needs

Nothing.

## Licence

MIT. Made by Jay Wright. [The Judgement OS page](https://unstuck-games.com/judgement-os/) has the whole story.
