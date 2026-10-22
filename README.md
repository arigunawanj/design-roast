# Design Roast

Brutal but constructive design roast with a 0-100 score, in Indonesian Gen Z voice. Checks visual hierarchy, fonts (interesting and readable, or just "basic"), color and contrast, trend check (kekinian atau usang), UX flow, duplicate information, responsive behavior, and animation, then gives concrete fixes for every finding.

Covers **UI/UX** (web, mobile, desktop app, dashboard), **static images** (poster, banner, feed, thumbnail, logo), and **video / motion**, each with its own scoring rubric.

For **educational designs** (e-learning, tutorials, slides, infographics, onboarding, explainer videos, educational Reels) there is an extra module based on the 12 **Mayer multimedia learning principles** (coherence, signaling, redundancy, spatial and temporal contiguity, segmenting, pre-training, modality, multimedia, personalization, voice, image), scored separately as a Learning Score.

Portable agent skill (`SKILL.md` standard). Works in **Claude Code, Codex, Gemini CLI, Antigravity, Cursor, GitHub Copilot, Windsurf, ChatGPT Projects**, and any agent that can read a markdown instruction file.

## Install

### One command, all agents (recommended)

```bash
curl -fsSL https://raw.githubusercontent.com/arigunawanj/design-roast/main/install.sh | sh
```

Installs globally to:

| Agent | Path |
|---|---|
| Claude Code | `~/.claude/skills/design-roast/` |
| Codex (and other `.agents`-aware agents) | `~/.agents/skills/design-roast/` |
| Gemini CLI | `~/.gemini/skills/design-roast/` |
| Antigravity | `~/.gemini/antigravity/skills/design-roast/` |

Per-project instead (run inside your repo; writes `.claude/`, `.agents/`, `.gemini/`, `.agent/` skill folders):

```bash
curl -fsSL https://raw.githubusercontent.com/arigunawanj/design-roast/main/install.sh | sh -s -- --project
```

Or with the [skills CLI](https://skills.sh) (detects installed agents):

```bash
npx skills add arigunawanj/design-roast
```

### Per agent

- **Claude Code (plugin)**: `/plugin marketplace add arigunawanj/design-roast` then `/plugin install design-roast@design-roast`.
- **Gemini CLI (extension)**: `gemini extensions install https://github.com/arigunawanj/design-roast`.
- **Codex**: copy `skills/design-roast/` to `~/.agents/skills/` (or `.agents/skills/` in a repo). Optionally merge [`adapters/AGENTS.md`](adapters/AGENTS.md) into your `AGENTS.md`.
- **Antigravity**: copy `skills/design-roast/` to `~/.gemini/antigravity/skills/` (global) or `.agent/skills/` (workspace).
- **Cursor**: copy [`adapters/.cursor/rules/`](adapters/.cursor/rules) and `skills/` into your repo.
- **GitHub Copilot**: copy [`adapters/.github/`](adapters/.github) and `skills/` into your repo.
- **Windsurf**: copy [`adapters/.windsurf/rules/`](adapters/.windsurf/rules) and `skills/` into your repo.
- **ChatGPT Projects**: paste [`CHATGPT_PROJECT_INSTRUCTIONS.md`](CHATGPT_PROJECT_INSTRUCTIONS.md) into Project Instructions and attach `skills/design-roast/SKILL.md`.
- **Anything else**: paste or attach [`skills/design-roast/SKILL.md`](skills/design-roast/SKILL.md) as system / custom instructions.

Adapters in `adapters/` (`AGENTS.md`, `CLAUDE.md`, `GEMINI.md`) are project-level pointers to the skill. Merge them into existing files, don't overwrite.

## Usage

Invoke by name (`/design-roast` where slash-skills are supported) or just ask naturally:

> Pakai Design Roast: roast landing page ini https://contoh.com. Cek hierarki, font, flow UX, informasi dobel, responsive, dan animasi. Kasih skor dan solusi yang konkret.

You can also attach a screenshot, a poster, or a video and ask for a roast. For agents without skill support, use the fill-in template [`prompts/ROAST_PROMPT.md`](prompts/ROAST_PROMPT.md).

## What you get

Final score out of 100 with a label, a scoreboard per category, roasts with specific location + reason + fix, a list of duplicated information, font recommendations with pairings, animation suggestions (element, duration, easing, trigger, library), prioritized fixes (quick win / medium / big), and a predicted score after the fixes. For educational designs you also get a Learning Score /100 across the 12 Mayer principles, and the final score is 70% Design Score + 30% Learning Score (default weights, adjustable on request). Principles that cannot be judged (for example Voice on a still image) are marked N/A, not guessed.

## Notes

- Output language is Indonesian (casual, Gen Z tone). It roasts designs, not people. Intensity can be softened ("roast halus") or raised ("tanpa ampun").
- The skill only judges what it can actually see. Anything it cannot check (animation from a still, other screen sizes, audio) is marked "tidak dinilai".
- Live URL review needs the agent to have browser tools; video review needs ffmpeg or an equivalent to extract frames.
- Skill discovery paths vary by agent version; if auto-activation doesn't kick in, reference the skill explicitly.

## License

MIT
