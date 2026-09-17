# AI Image Realism Skill

English | [简体中文](./README.zh-CN.md)

Make existing AI portraits, product images, and marketing visuals look more natural by fixing plastic skin, malformed hands and faces, repeated textures, and inconsistent lighting, from inside Claude Code, Codex, or OpenClaw.

> [!IMPORTANT]
> Rendering needs a [Beatra](https://beatra.ai) account and uses credits. The skill itself is free to install.

| Question | Answer |
| --- | --- |
| **What it does** | Make existing AI portraits, product images, and marketing visuals look more natural by fixing plastic skin, malformed hands and faces, repeated textures, and inconsistent lighting. |
| **Requirements** | Python 3.10+ and an agent that loads `SKILL.md` |
| **Cost** | Free to install. Each render uses credits on your Beatra account, and paid steps run only when you ask for that exact render or approve its card. |
| **Works with** | Claude Code, Codex, OpenClaw |

| Skill | Entry point | Version |
| --- | --- | --- |
| [`ai-image-realism`](skills/ai-image-realism) | [SKILL.md](skills/ai-image-realism/SKILL.md) | 0.2.7 |

This repository is published automatically from [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/ai-image-realism). Report issues there.

## Install

With the [`skills`](https://skills.sh) CLI:

```bash
npx skills add beatra-ai/ai-image-realism-skill
```

With the GitHub CLI:

```bash
gh skill install beatra-ai/ai-image-realism-skill ai-image-realism
```

Or clone this repository and copy `skills/ai-image-realism` into `~/.claude/skills/` for Claude Code,
`~/.agents/skills/` for Codex, or `~/.openclaw/skills/` for OpenClaw.

Or paste this into your agent:

```text
Install the ai-image-realism skill from https://github.com/beatra-ai/ai-image-realism-skill (folder skills/ai-image-realism), then follow its SKILL.md to connect my Beatra account.
```

## What you get

- **Diagnose before changing** — Review anatomy, texture, lighting, background, composition, text, and destination fit, then focus on the one problem cluster that matters most.
- **Repair the smallest useful area** — Choose a targeted local repair or a whole-image texture pass instead of replacing a nearly accepted image.
- **Protect what already works** — Keep identity, product shape, brand details, composition, and unaffected areas recognizable where possible.

## Use cases

- **Naturalize AI portraits** — Reduce plastic-looking skin, repair hands and facial details, and keep the person's accepted appearance recognizable where possible.
- **Refine product and e-commerce images** — Correct reflections, material texture, shadows, and background repetition while keeping product shape, color, packaging, and brand marks recognizable where possible.
- **Polish marketing and ad visuals** — Fix distracting artifacts and inconsistent light while keeping the selected message, layout, and key visual recognizable where possible.
- **Clean up social covers** — Make feed and cover images feel less templated while keeping the crop, safe areas, subject, and text layout recognizable where possible.

## FAQ

### What kinds of AI image problems can it repair?

It focuses on visible artifacts such as plastic-looking skin, distorted hands and faces, repeated textures, inconsistent lighting, and formulaic backgrounds while keeping accepted details recognizable where possible.

### How does it choose between a local fix and a whole-image refinement?

It matches the edit to the visible problem: focused local repair for a specific defect, whole-image refinement for texture or lighting, and a new composition when you want a broader reinterpretation.

### Can it preserve a person's identity or a product's branding?

It records identity, product shape, color, packaging, and brand marks as must-keep details, then compares the result with the original and checks those details for drift.

### How are text, logos, hands, and faces reviewed after retouching?

It targets the named defect, keeps the rest recognizable, and visually reviews typography, logo geometry, anatomy, identity, and the corrected area against the original.

## Updates

Each installed skill checks for a new version at most once a day, verifies the
official archive before replacing itself, and leaves your installation untouched
if anything fails. Turn it off at any time — see
`references/automatic-updates-and-safety.md` inside the skill.

## License

[MIT-0](LICENSE) — free to use, modify, and redistribute, including
commercially. No attribution required. Same terms as these skills carry on
ClawHub.
