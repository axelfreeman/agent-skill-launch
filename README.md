# 🚀 Agent Skill Launch — the marketer's playbook for shipping AI-agent skills

**You built a skill. Nobody installed it. Here's why — and the fix.**

[![skills.sh](https://skills.sh/b/axelfreeman/agent-skill-launch)](https://skills.sh/axelfreeman/agent-skill-launch)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---

Most "agent skills" are a SKILL.md that gets committed and forgotten. A few get thousands of installs. The difference isn't the code — it's three levers most builders never touch.

## The three levers

### 1. Distribution is install-driven, not crawled
[skills.sh](https://skills.sh) — the agent-skill directory (~10k skills, 1.3M+ installs) — doesn't crawl GitHub to find you. A repo appears on its leaderboard **only after someone runs `npx skills add owner/repo`**. That install fires telemetry, and **installs decide ranking, not stars**.

→ Seed your own skill once. It's the difference between invisible and discoverable.

### 2. The `description` is the entire funnel
The frontmatter `description` is read by Claude Code, Cursor, and skills.sh to decide **when the skill fires**. Write it as a long list of trigger situations — "Use when the user asks for …" — not a summary of what the skill does.

**Wrong:** *"GitHub profile setup for non-programmers."*

**Right:** *"Set up a GitHub profile and repo for a non-programmer … Use when a marketer or solopreneur wants to create or polish their GitHub presence, or publish their first repo without touching a terminal."*

### 3. One memorable hook
Skills that get cited and reposted carry a single quotable rule. A feature list doesn't travel; a hook does. Find your one line.

## What's inside

This repo is a SKILL.md that encodes the full playbook. Load it into any agent (Claude Code, Cursor, Codex, Gemini CLI, Hermes) and it will:

- Write the SKILL.md correctly — `description` as the firing trigger.
- Distribute it through skills.sh — seed, badge, verify.
- Keep the repo clean — gitignore the byproducts.

## Install

```bash
git clone https://github.com/axelfreeman/agent-skill-launch.git
mkdir -p ~/.agents/skills
ln -s "$PWD/agent-skill-launch" ~/.agents/skills/agent-skill-launch
```

Or install directly:

```bash
npx skills add axelfreeman/agent-skill-launch
```

## Who this is for

- Marketers and founders shipping an AI-agent skill or AI-native product.
- Indie hackers who want their skill to earn installs, not just stars.
- Anyone asking "why did that skill go viral and mine didn't".

## License

MIT — use it, ship it, quote it.

*By [Axel Freeman](https://axelfreeman.com) — AI-native marketer.*
