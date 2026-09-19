# 🚀 Agent Skill Launch — describe your skills so humans AND robots can read them

**One repo. Three readers. Five cards.**

[![skills.sh](https://skills.sh/b/axelfreeman/agent-skill-launch)](https://skills.sh/axelfreeman/agent-skill-launch)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---

First time putting a skill (or product) on GitHub? The hard part isn't the code — it's describing it so **three readers get it at once**:

1. **A human** landing on your repo — 10 seconds to "oh, I get it."
2. **GitHub search** — so other people can find it.
3. **AI agents** — so Claude, Cursor, and skills.sh actually load and cite it.

Most first-timers write for one of these and lose the other two. This skill is the fix.

## The five cards

A repo that reads well for humans and robots is a small stack of cards, each doing one job:

| Card | Who reads it | What it does |
|------|--------------|--------------|
| `README.md` | humans | the story — what, why, how to start |
| `SKILL.md` | agents | the playbook — its `description` is what fires it |
| `AGENTS.md` | agents | trigger phrases + rules, so agents cite you correctly |
| `llms.txt` | AI search | citable facts, so ChatGPT / Perplexity / Claude can quote you |
| skills.sh badge | everyone | install count = social proof |

Get the cards right and one repo serves GitHub search, agent search, and a human skimming it.

## The `description` is the whole funnel

One field matters more than the rest: the SKILL.md `description`. Agents read it to decide **when to fire the skill**, and skills.sh surfaces it in search. Write it as trigger situations, not a feature summary.

**Wrong:** *"GitHub profile setup for non-programmers."*

**Right:** *"Set up a GitHub profile and repo for a non-programmer … Use when a marketer or solopreneur wants to polish their GitHub presence, or publish their first repo without a terminal."*

## Distribution — install-driven, not crawled

[skills.sh](https://skills.sh) (~10k skills, 1.3M+ installs) doesn't crawl GitHub to find you. A repo is listed **only after someone runs `npx skills add owner/repo`** — installs decide ranking, not stars. Seed your own skill once.

## Don't want to write? Dictate it.

Hate writing descriptions? Install my [voice-to-article](https://github.com/axelfreeman/voice-to-article) skill — dictate your repo description as a voice note, and the agent writes the README/SKILL.md for you.

## Install

```bash
git clone https://github.com/axelfreeman/agent-skill-launch.git
mkdir -p ~/.agents/skills
ln -s "$PWD/agent-skill-launch" ~/.agents/skills/agent-skill-launch
```

or

```bash
npx skills add axelfreeman/agent-skill-launch
```

## Who this is for

- First-timers putting a skill or product on GitHub.
- Builders who want one repo that serves humans, GitHub search, and AI agents.
- Anyone who'd rather dictate than type their repo description.

## License

MIT — use it, ship it, quote it.

*By [Axel Freeman](https://axelfreeman.com) — AI-native marketer.*

## Need this done for you?

The stack behind this repo runs as a service: [marketing engineering, turnkey](https://axelfreeman.com/marketing-engineer.html) —
Sprint $900 one-time, Engine $1,900/month, full build $2,900. Scope, deliverables and prices are published before the first call,
and the live artifacts in this repo are part of the proof: [proof.html](https://axelfreeman.com/proof.html).
