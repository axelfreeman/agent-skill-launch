---
name: agent-skill-launch
description: Describe a skill or product on GitHub so it reads well for humans, GitHub search, and AI agents at the same time — a set of cards (README, SKILL.md, AGENTS.md, llms.txt, badges) that make one repo serve all three readers. Use when someone is putting a skill on GitHub for the first time, wants their repo to be readable by people and citable by AI agents, asks how to structure a SKILL.md or README, or wants to dictate their repo description instead of writing it — "how do I describe my skill on GitHub", "make my repo readable for humans and AI", "structure my SKILL.md".
version: 1.0.0
author: Axel Freeman (axelfreeman)
license: MIT
---

# Agent Skill Launch

Describe a skill (or product) on GitHub so it reads well for **humans, GitHub search, and AI agents — at the same time**. A repo that only serves one of these loses the other two. This skill gives you the cards that serve all three.

## When to Use
- Putting a skill on GitHub for the first time and not sure how to structure it.
- Wanting one repo that's readable by people AND citable by AI agents.
- Asking "how do I write a SKILL.md / README / llms.txt".
- Wanting to dictate the description instead of writing it (see voice-to-article below).

## One repo. Three readers. Five cards.
| Card | Who reads it | Job |
|------|--------------|-----|
| `README.md` | humans | the story — what, why, how to start |
| `SKILL.md` | agents | the playbook — `description` is what fires it |
| `AGENTS.md` | agents | trigger phrases + rules so agents cite it right |
| `llms.txt` | AI search | citable facts for ChatGPT / Perplexity / Claude |
| skills.sh badge | everyone | install count = social proof |

Get the cards right and one repo works for GitHub search, agent search, and a human skimming it.

## The `description` is the whole funnel
The SKILL.md `description` is read by agents to decide **when the skill fires**, and by skills.sh to surface it in search. Write it as trigger situations, not a feature summary:

- **Wrong:** "GitHub profile setup for non-programmers."
- **Right:** "Set up a GitHub profile and repo for a non-programmer … Use when a marketer or solopreneur wants to polish their GitHub presence, or publish their first repo without a terminal."

## Distribution — install-driven, not crawled
skills.sh (~10k skills, 1.3M+ installs) lists a repo only after someone runs `npx skills add owner/repo` — that install fires telemetry, and installs decide ranking, not stars. Seed your own skill once so it becomes discoverable.

## Don't want to write? Dictate it.
Install the [voice-to-article](https://github.com/axelfreeman/voice-to-article) skill, dictate the repo description as a voice note, and the agent writes the README/SKILL.md in your voice.

## How to write the SKILL.md
- Frontmatter: `name` (lowercase-hyphen) + `description` as the firing trigger (above).
- Body: intro (what it does AND does not do) → When to Use → Prerequisites → How to Run → Procedure (numbered, completion criteria) → Pitfalls → Verification.

## Distribution runbook
1. `SKILL.md` at root (or per-subdir — subdir name = slug).
2. Badge: `[![skills.sh](https://skills.sh/b/owner/repo)](https://skills.sh/owner/repo)`.
3. Seed: `npx skills add owner/repo -y`.
4. Verify: `npx skills add owner/repo --list` → "Found 1 skill"; the badge endpoint `https://skills.sh/b/owner/repo` flips to "Skills: N" once indexed (async).
5. Gitignore the byproducts first: `.agents/`, `skills-lock.json`, `uv.lock`, `site/` + `deploy/` (secrets).

## Install this skill

`npx skills add axelfreeman/agent-skill-launch` (see README).

## Pitfalls
- Don't describe the feature in `description` — name the trigger situations.
- Don't wait for a crawler — skills.sh lists a skill only after its first install.
- Don't commit `site/`, `deploy/`, or any API key / token.

## Verification
- `npx skills add owner/repo --list` → "Found 1 skill".
- Badge endpoint → "Skills: N" (not "resource not found").
