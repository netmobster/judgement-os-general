# sexyhtml

House styles for finished HTML pages. Part of [Judgement OS](https://unstuck-games.com/judgement-os/), the General Edition: a second opinion for your Claude Code skills, only when they need one. (*Not an operating system.*)

## What it does

Ask for a page and /sexyhtml picks the house style and the shape: a report, a checklist, a picker, an explainer, a one-pager or a multiple-choice report. When a request reads two ways, the judges weigh in. Each style brings its own component kit: callouts, stat rows, timelines, question panels, charts and slide frames.

## Install

In Claude Code:

```
/plugin marketplace add netmobster/judgement-os-general
/plugin install sexyhtml@judgement-os
```

The other seven plugins are in the same marketplace; [the README](https://github.com/netmobster/judgement-os-general) lists them all.

## Use it

| What | Does |
|---|---|
| `/sexyhtml` | The router: say what you want, it picks the style and shape. |
| `/sexyhtml:jay` | ECHO-JAY, the default: light industrial, gold and steel blue. |
| `/sexyhtml:seren` | Seren, for games: ink, bone, copper and verdigris. |
| `/sexyhtml:judgement-os` | The Judgement OS brand, by name only. |

## Examples

```
/sexyhtml a one-page status report of this repo
make me a checklist page for the release
```

## What it needs

Nothing. Pages publish as Claude artifacts where the surface has them.

## Licence

MIT. Made by Jay Wright. [The Judgement OS page](https://unstuck-games.com/judgement-os/) has the whole story.
