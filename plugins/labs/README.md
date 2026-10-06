# labs

The Judgement OS core: two judges, a recorder and a log. Part of [Judgement OS](https://unstuck-games.com/judgement-os/), the General Edition: a second opinion for your Claude Code skills, only when they need one. (*Not an operating system.*)

## What it does

Skills in Judgement OS make most decisions with a plain rule. At the few marked decisions where the right answer depends on you, and the rule can't tell, labs asks two judges (a small model and a big one) one bounded question each. The recorder checks every answer in code and combines the two; you only hear about it when both disagree with the rule. Every call goes in an append-only log on your machine.

## Install

In Claude Code:

```
/plugin marketplace add netmobster/judgement-os-general
/plugin install labs@judgement-os
```

The other seven plugins are in the same marketplace; [the README](https://github.com/netmobster/judgement-os-general) lists them all.

## Use it

| What | Does |
|---|---|
| `/labs:profile` | Writes the one file the judges read about you, a question at a time. No judge is asked until it exists. |
| `/labs:try` | Puts both judges on a morning, blind. You pick the better answer, then see which model wrote it. |
| the second-opinion agent | What the other plugins call at a marked decision. You don't call it yourself. |

## Examples

```
/labs:profile
/labs:try today
```

## What it needs

Nothing else. The other plugins use labs when it's installed and carry on with their rules when it isn't.

## Licence

MIT. Made by Jay Wright. [The Judgement OS page](https://unstuck-games.com/judgement-os/) has the whole story.
