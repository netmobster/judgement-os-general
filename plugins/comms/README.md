# comms

The send gate, humanify and Slack polling. Part of [Judgement OS](https://unstuck-games.com/judgement-os/), the General Edition: a second opinion for your Claude Code skills, only when they need one. (*Not an operating system.*)

## What it does

The send gate is a hook that stops every outbound message (Slack, email and the like) until you type send yourself. Humanify takes the AI tics out of a draft, in the register that fits where it's going. Poll reads the Slack channels you pick and drafts replies that post only when you approve the exact text.

## Install

In Claude Code:

```
/plugin marketplace add netmobster/judgement-os-general
/plugin install comms@judgement-os
```

The other seven plugins are in the same marketplace; [the README](https://github.com/netmobster/judgement-os-general) lists them all.

## Use it

| What | Does |
|---|---|
| `/comms:humanify` | A de-tic pass for a draft. |
| `/comms:poll` | Reads your chosen Slack channels and drafts replies. Sets the channels up on first run. |
| the send gate | A hook. Nothing to type: an outbound message waits until you say send. |

## Examples

```
/comms:humanify (paste a draft)
/comms:poll
```

## What it needs

Poll needs Claude's Slack connector. The gate and humanify need nothing.

## Licence

MIT. Made by Jay Wright. [The Judgement OS page](https://unstuck-games.com/judgement-os/) has the whole story.
