# Judgement OS: General Edition

A second opinion for your Claude Code skills, only when they need one. The "OS" is a joke; the plugins aren't.

Version 0.2.2 · MIT · made by Jay Wright · [the Judgement OS page](https://netmobster.github.io/unstuck-games/judgement-os/)

## What it does

Your skills run their steps, same as always. At the few decisions where the right answer depends on you, or on
something nobody could know when the skill was written, a rule picks first. When the rule can't tell, two judges
read your profile and answer one small question. You only hear about it when both disagree with the rule and both
mean it. Every call is logged on your machine, so you can see what happened and teach the rules what they keep
missing.

The judges recommend. They never authorise: they can't send a message, deploy, merge or touch protected files, and
the guard's hard rules run as hooks, not instructions.

## Install

In Claude Code:

```
/plugin marketplace add netmobster/judgement-os-general
/plugin install labs@judgement-os
/plugin install guard@judgement-os
/plugin install sexyhtml@judgement-os
/plugin install make@judgement-os
/plugin install comms@judgement-os
/plugin install day@judgement-os
/plugin install dice@judgement-os
/plugin install gears@judgement-os
```

Install all of them, or just the ones you want. `labs` is the core; the others use it when it's there and carry on
when it isn't.

Then run `/labs:profile` and write a few lines about how you work. Until your profile exists, the rules run on their
own.

## What's in it

- **labs**: The Judgement OS core: two judges consulted at marked decisions inside skills, the recorder that checks every answer and combines the two, the append-only log, /labs:profile, the one file the judges read about you, and /labs:try, which puts both judges on a morning blind so you can see which one you trust.
- **guard**: Hard rules as hooks: deploys are printed for you to run, destructive commands and secrets ask first, state files change only through their scripts, and a session is archived only when you say so.
- **sexyhtml**: House styles for finished HTML pages. /sexyhtml picks the style (ECHO-JAY by default, Seren for games) and the shape, with the Judgement OS weighing in when a request reads two ways; or name one: /sexyhtml:jay, /sexyhtml:seren, /sexyhtml:judgement-os.
- **make**: Say what you want made, and it lands in the right place, in your look: a page, a form or card in the chat, a deck, a design, a living doc, a file or a design system. /make picks where it lands, with the Judgement OS weighing in when a request reads two ways, then hands it to the right maker. Pages go to sexyhtml.
- **comms**: The send gate, which stops every outbound message until you type send; humanify, a de-tic pass for drafts written with AI in the room; and poll, which reads the Slack channels you choose and drafts replies that post only when you approve them.
- **day**: A day loop for Claude Code: a short boot with the judges on the style pick, mid-day and end-of-day check-ins from your TASKS.md, habits you set up once, a daily reading and a phrase in a language you're learning, /flag for work you want to come back to, and a clock on every message.
- **dice**: Real dice for tabletop games: any notation, advantage and disadvantage, damage, ability scores, never an invented roll. And nine party games to play with Claude: /dice:play.
- **gears**: Thinking tools built by Jay Wright: gears, loops and modes through one router, or by name with /gears:gear. Add your own beside your profile. selfActual users get more, working from their live profile: see selfactual.ai.

## What it needs

No account. A profile file you write yourself, and a `TASKS.md` if you want the day loop. `/comms:poll` needs
Claude's Slack connector. The judges use Claude Sonnet and Claude Opus by default, and you can change both in your
settings. Your settings and state live in `~/.claude/judgement-os/`: habits, the daily reading and phrase, and the
judges' log included.

## What it isn't, yet

It's young: in daily use since October 2026, first by its author, then by a few alpha users. The log is short, and
every claim about it comes from that log.

## Read more

- [The Judgement OS page](https://netmobster.github.io/unstuck-games/judgement-os/)
- [How it was built, in six posts](https://echofiles.substack.com/p/how-do-i-turn-my-claude-code-setup), on The ECHO Files
- [How to add judgement to your own skills](https://echofiles.substack.com/p/how-do-i-add-judgement-to-my-own) (out Sun 11 Oct)

## Credit

MIT. If you build on the pattern, credit Judgement OS and link back here. That's the whole ask.
