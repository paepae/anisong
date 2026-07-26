# อานิสงส์ · Anisong

*Open-source karma for your AI agents.*

A distilled toolkit of skills for personal and family AI — the parts worth keeping
from a lot of community tinkering, cleaned up and given back. *Anisong* (Thai/Pali:
the fruit of merit) is what flows back to you from a good deed. This is mine,
returned.

## What it is

Anisong is a small, opinionated toolkit for running your own AI agents — the skills,
prompts, and glue that turn a bare model into something that can actually *do* things
around a home or a homelab. It is built for personal and family use first: the kind of
setup where one assistant helps the household and a couple of others handle developer
and knowledge work, all on hardware you own.

It is **a distillation, not a framework.** Most of what is here started as something
learned, borrowed, or pieced together from the open-source and self-hosting
communities — then used in anger, trimmed to the parts that earned their place, and
documented so the next person does not have to rediscover them.

It is modular: take the one piece you need, ignore the rest. It assumes you bring your
own model and your own agents. Anisong is the kit they reach into, not the agent
itself.

What it is **not**: a hosted product, a do-everything platform, or anything tied to one
vendor's model. A personal collection made public — held to a real-use bar, personal in
scope.

## Skills

| Skill | What it does |
|---|---|
| [`lean-writing`](skills/lean-writing/SKILL.md) | The snapshot contract for every file an agent writes: current state only, with the story of how it got that way routed to git, the ticket, and the closing summary. Keeps changelog prose, "Update:" layers, and stale claims out of code, docs, and READMEs. |

## Install

As a plugin, in Claude Code:

```
/plugin marketplace add paepae/anisong
/plugin install anisong@anisong
```

Or take a single skill: each one is a self-contained directory of plain markdown, so
copying `skills/<name>/` into the directory your agent loads skills from — `~/.claude/skills/`
for Claude Code — is a complete install.

Pick one of the two per skill. A plugin install and a hand-placed copy of the same
skill both load, and the agent sees it twice.

## Why the name

**อานิสงส์ (anisong)** is a Thai word, from the Pali *ānisaṃsa*: the **beneficial fruit
of merit** — the good that flows back to you from a good deed. In Thai Buddhist culture
it is the everyday word for the *returns* of generosity: you give, and something comes
back, to you and to others.

That is the whole idea of this project in one word. Almost everything here was
*received* — from communities, maintainers, and strangers who wrote down what they
figured out. Distilling it and publishing it back is the merit returned: the fruit
flows on. A toolkit that gives back what the community gave it is, quite literally,
อานิสงส์.

There is also a wink in the romanization. **"Anisong"** reads, to an English speaker, a
lot like **"anime song."** That is deliberate — it keeps a word that could sound lofty
feeling light and approachable, which is the spirit the project is going for. (It is
not, to be clear, about anime songs. Though no one will stop you from running it to
one.)

## License

MIT — see [LICENSE](LICENSE).
