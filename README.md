# AI Progress Update (APU)

APU is a small family of portable skills that teaches an AI agent to report progress clearly, honestly, and at the right level of detail.

It works for coding, research, migrations, audits, content production, data work, and other multi-step tasks. It is especially useful when a task runs long enough that “still working” is no longer a satisfying update.

> [!TIP]
> **AI agent reading this repository?** Read [AGENTS.md](AGENTS.md) before installing, adapting, or editing APU. Help the user choose one mode, use the complete skill directory, and verify the result instead of merely describing an installation.

## Pick your mode

| Skill | Best for | Typical update |
| --- | --- | --- |
| **APU Lite** | Quick tasks and low-noise status pulses | One compact line |
| **APU AvgJoe** | Everyday multi-step work | A balanced 6–8 line status card |
| **APU Chad** | Long-running, risky, or closely supervised work | Detailed checkpoints, evidence, risks, and scope reconciliation |

All three modes follow the same accounting rule: show a percentage only when there is a credible denominator, and count only confirmed outcomes.

### APU Lite

```text
APU Lite — Checkpoint 12/14: Auth Hardening | Total 19/20 (95%) | On track | Next: verify token rotation
```

### APU AvgJoe

```markdown
### APU AvgJoe — On track

- **Checkpoint:** 12/14 — Auth Hardening
- **Overall:** 19/20 confirmed (95%)
- **Since last update:** Closed refresh-token replay.
- **In progress:** Running focused authentication checks.
- **Next:** Reconcile the final check.
- **Blockers:** None.
- **Verified:** 18 focused checks pass; full suite pending.
```

### APU Chad

APU Chad adds a real baseline, delta since the previous report, active work, specific evidence, unverified areas, next acceptance gate, risks, approval needs, confidence, and final scope reconciliation.

## Install in your AI tool

Each mode is a standalone [Agent Skill](https://agentskills.io). Choose one mode and copy its complete directory—not only `SKILL.md`—to the personal or project location supported by your tool.

| AI tool | Personal/global location | Project location | Invocation |
| --- | --- | --- | --- |
| **OpenAI Codex** | `~/.codex/skills/<mode>/` | `.agents/skills/<mode>/` | `$apu-chad` or automatic matching |
| **Claude Code** | `~/.claude/skills/<mode>/` | `.claude/skills/<mode>/` | `/apu-chad` or automatic matching |
| **Cursor** | `~/.cursor/skills/<mode>/` | `.cursor/skills/<mode>/` | `/apu-chad` or automatic matching |
| **GitHub Copilot** | `~/.copilot/skills/<mode>/` | `.github/skills/<mode>/` | `/apu-chad` or automatic matching |
| **Gemini CLI** | Import from `~/.gemini/GEMINI.md` | Import from the project `GEMINI.md` | Loaded as persistent context |

Replace `<mode>` with `apu-lite`, `apu-avgjoe`, or `apu-chad`.

The source directories in this repository are:

```text
skills/apu-lite
skills/apu-avgjoe
skills/apu-chad
```

The `agents/openai.yaml` file is optional Codex UI metadata. Other tools can safely ignore it while retaining the whole directory for portability.

### OpenAI Codex

Ask Codex:

```text
Use $skill-installer to install APU Chad from
https://github.com/abselon/ai-progress-update/tree/main/skills/apu-chad
```

Or copy the selected directory to `~/.codex/skills/`. Invoke it with `$apu-chad`; implicit invocation is allowed when a task matches the skill description. Restart Codex only if a newly installed skill does not appear.

See the [Codex skills documentation](https://learn.chatgpt.com/docs/build-skills).

### Claude Code

Copy the selected directory to `~/.claude/skills/` for personal use or `.claude/skills/` inside a project. Claude can load it automatically from its description or explicitly with `/apu-chad`.

Ask Claude Code:

```text
Install APU Chad globally from
https://github.com/abselon/ai-progress-update/tree/main/skills/apu-chad
Copy the complete skill directory to ~/.claude/skills/apu-chad,
verify SKILL.md is present, and report the installed path.
```

See the [Claude Code skills documentation](https://code.claude.com/docs/en/skills).

### Cursor

Copy the selected directory to `~/.cursor/skills/` for personal use or `.cursor/skills/` inside a project. Cursor can discover Agent Skills automatically and also supports explicit invocation from its slash-command menu.

Ask Cursor:

```text
Install APU Chad globally from
https://github.com/abselon/ai-progress-update/tree/main/skills/apu-chad
Copy the complete skill directory to ~/.cursor/skills/apu-chad,
verify SKILL.md is present, and report the installed path.
```

Cursor also reads this repository’s `AGENTS.md` and `CLAUDE.md`. See [Cursor Agent Skills](https://cursor.com/docs/skills) and [Cursor rules](https://cursor.com/docs/context/rules).

### GitHub Copilot

Copy the selected directory to `~/.copilot/skills/` for personal use or `.github/skills/` inside a project. Compatible Copilot agents load a relevant skill automatically or accept `/apu-chad`.

Ask Copilot:

```text
Install APU Chad as a personal skill from
https://github.com/abselon/ai-progress-update/tree/main/skills/apu-chad
Copy the complete directory to ~/.copilot/skills/apu-chad,
verify SKILL.md is present, and report the installed path.
```

See GitHub’s [Agent Skills documentation](https://docs.github.com/en/copilot/how-tos/copilot-on-github/customize-copilot/customize-cloud-agent/add-skills).

### Gemini CLI

Gemini CLI documents persistent instructions through `GEMINI.md`. Copy the chosen APU directory somewhere stable, then import its `SKILL.md` from your personal `~/.gemini/GEMINI.md`:

```markdown
@./skills/apu-chad/SKILL.md
```

With that example, place the complete skill at `~/.gemini/skills/apu-chad/`. For project-only use, use the same import pattern from the project’s root `GEMINI.md`.

This loads APU as persistent context rather than a dynamically selected skill. See the [Gemini CLI context-file documentation](https://google-gemini.github.io/gemini-cli/docs/cli/gemini-md.html).

### Other AI agents

If an agent supports the open Agent Skills format, give it the URL of the chosen mode and ask it to install the complete directory into its documented personal or project skill location. If it does not support Agent Skills, attach or import the chosen `SKILL.md` as persistent instructions.

Use this portable installation request:

```text
Install APU Chad for this AI tool from
https://github.com/abselon/ai-progress-update/tree/main/skills/apu-chad
Use the tool's documented personal/global skill location.
Copy the complete directory, preserve its contents, verify discovery,
and report exactly what was installed and what was not tested.
```

Never run installation commands from an untrusted fork without inspecting its `SKILL.md` and any bundled scripts first.

## Fork it and make it yours

APU is intentionally opinionated but portable. Fork this repository and tune it to your own working style:

1. Change cadence, labels, confidence rules, or update templates.
2. Keep checkpoint position separate from overall completion.
3. Preserve honest scope-change and verification rules.
4. Run the official skill validator on every edited skill.
5. Publish your fork on GitHub so your team—or the wider community—can install it.

Good forks might add team-specific release gates, research confidence levels, creative-production stages, or a fourth mode. Avoid embedding secrets, private paths, client data, or rules that falsely imply work was verified.

If your fork becomes something new, rename the skill folder, the `name` in `SKILL.md`, and the `$skill-name` in `agents/openai.yaml`.

## Repository layout

```text
AGENTS.md
CLAUDE.md
GEMINI.md
.github/
└── copilot-instructions.md
skills/
├── apu-lite/
├── apu-avgjoe/
└── apu-chad/
```

Each skill folder is independently installable. The root instruction files help AI agents work on this repository; they are not additional APU modes.

## License

[MIT](LICENSE) — use it, fork it, improve it, and share what you build.
