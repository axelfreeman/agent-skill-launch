---
name: agent-skill-launch
description: Launch an AI-agent skill that agents actually load and people actually install — write a SKILL.md whose description fires in agents, distribute it through skills.sh, and give it one memorable hook. Use when someone is about to ship a skill, wants their agent skill or AI product to get noticed, asks how to get listed on skills.sh, or needs a marketing playbook for an agent skill — "launch my skill", "get my skill on skills.sh", "skill distribution", "agent skill marketing".
version: 1.0.0
author: Axel Freeman (axelfreeman)
license: MIT
---

# Agent Skill Launch

The marketer's playbook for shipping an AI-agent skill (SKILL.md) that gets loaded and installed — not just committed. Built from a teardown of skills that took off in August 2026 and the ones that didn't.

## When to Use
- About to ship a SKILL.md and want it to reach agents.
- Want a skill/product to earn installs, not just sit in a repo.
- Asking "how do I get on skills.sh" or "why did that skill go viral".

## The three levers
1. **Distribution is install-driven, not crawled.** A repo appears on the skills.sh leaderboard only after someone runs `npx skills add owner/repo` — that install fires telemetry, and installs (not stars) decide ranking. Seed your own skill once so it becomes discoverable.
2. **The `description` fires the skill.** Claude Code, Cursor, and skills.sh all read the frontmatter `description` to decide when to load the skill. Write it LONG, naming trigger situations ("Use when the user asks for / wants to …"), never a capability summary.
3. **One memorable hook.** Skills that get cited and reposted have a single quotable rule — not a feature list. Example that worked: "prose is authored, counts are measured" plus a drift counter that fails CI when the map rots. Pick one line someone can quote.

## How to write the SKILL.md
- Frontmatter: `name` (lowercase-hyphen) + a `description` written as the firing trigger (above).
- Body: intro (what it does AND does not do) → When to Use (+ don't-use counter-triggers) → Prerequisites → How to Run → Procedure (numbered, each step with a completion criterion) → Pitfalls → Verification.
- Keep SKILL.md scannable. Push detail into `references/`, executables into `scripts/`, files-to-copy into `assets/`.

## How to distribute (runbook)
1. Ship `SKILL.md` at repo root (or one SKILL.md per subdir — the subdir name becomes the skill slug).
2. Add the badge to README: `[![skills.sh](https://skills.sh/b/owner/repo)](https://skills.sh/owner/repo)`.
3. Seed the listing: `npx skills add owner/repo -y`.
4. Verify: `npx skills add owner/repo --list` prints "Found 1 skill"; `curl https://skills.sh/b/owner/repo` flips from "resource not found" to "Skills: N" once indexed (async, minutes–hours).
5. Gitignore the byproducts first: `.agents/`, `skills-lock.json`, `uv.lock`, and any `site/` + `deploy/` (they can hold secrets).

## Install this skill
Symlink so `git pull` updates it:
`ln -s "$PWD" ~/.agents/skills/agent-skill-launch`

## Pitfalls
- Don't describe the feature in `description` — name the situations that should fire it.
- Don't wait for a crawler — skills.sh lists a skill only after its first install.
- Don't commit `site/`, `deploy/`, or any API key / token.

## Verification
- `npx skills add owner/repo --list` returns "Found 1 skill".
- The badge endpoint returns "Skills: N" (not "resource not found").
