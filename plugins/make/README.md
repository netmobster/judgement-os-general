# make

The front door for making things. Part of [Judgement OS](https://unstuck-games.com/judgement-os/), the General Edition: a second opinion for your Claude Code skills, only when they need one. (*Not an operating system.*)

## What it does

Say what you want made and /make picks where it lands: a page, a form or card in the chat, a deck, a design, a living doc, a file or a design system, then hands it to the right maker. Pages go to sexyhtml. When a request points two ways, the judges weigh in.

## Install

In Claude Code:

```
/plugin marketplace add netmobster/judgement-os-general
/plugin install make@judgement-os
```

The other seven plugins are in the same marketplace; [the README](https://github.com/netmobster/judgement-os-general) lists them all.

## Use it

| What | Does |
|---|---|
| `/make` | The front door. |
| `/make:diff-review` | A visual review of a branch, commit or the working tree, every claim citing a file and line. |
| `/make:plan-review` | A plan read against the real code, ending in approve, revise or reject. |
| `/make:project-recap` | A recap for someone coming back to a project. |
| `/make:fact-check` | Checks every claim on a page against the code and history, and fixes it in place. |
| `/make:guide` | A checker page that walks you through each make tool once and keeps your answers. |

## Examples

```
/make a deck from these notes
/make ask me in chat which option to ship
/make:diff-review main..HEAD
```

## What it needs

Nothing. Decks, designs and docs use the artifact types your Claude account offers.

## Licence

MIT. Made by Jay Wright. [The Judgement OS page](https://unstuck-games.com/judgement-os/) has the whole story.
