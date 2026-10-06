# guard

Hard rules as hooks. Part of [Judgement OS](https://unstuck-games.com/judgement-os/), the General Edition: a second opinion for your Claude Code skills, only when they need one. (*Not an operating system.*)

## What it does

A PreToolUse hook that checks every shell command, file write and connector call before it runs. Deploys are printed for you to run yourself; destructive commands and anything that looks like a secret ask first; the Judgement OS state files change only through their own scripts; and a session is archived only when you say so.

## Install

In Claude Code:

```
/plugin marketplace add netmobster/judgement-os-general
/plugin install guard@judgement-os
```

The other seven plugins are in the same marketplace; [the README](https://github.com/netmobster/judgement-os-general) lists them all.

## Use it

| What | Does |
|---|---|
| `/guard:guard` | Explains what was stopped and why, when a tool call comes back with a "guard:" reason. |

## Examples

```
/guard:guard
rm -rf build   (asks before it runs)
```

## What it needs

Nothing. Optional: name folders in your settings (guard.protectMain) where committing on main is refused.

## Licence

MIT. Made by Jay Wright. [The Judgement OS page](https://unstuck-games.com/judgement-os/) has the whole story.
