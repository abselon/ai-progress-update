# AI Progress Update (APU)

APU is a small family of portable skills that teaches an AI agent to report progress clearly, honestly, and at the right level of detail.

It works for coding, research, migrations, audits, content production, data work, and other multi-step tasks. It is especially useful when a task runs long enough that “still working” is no longer a satisfying update.

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

## Install

Each mode is a standalone Codex skill. Install one mode or all three from this repository with the Codex skill installer, or copy the complete chosen folder into:

```text
~/.codex/skills/<skill-name>/
```

Example repository paths:

```text
skills/apu-lite
skills/apu-avgjoe
skills/apu-chad
```

Restart Codex after a manual copy so it rediscovers the skill. Then invoke a mode explicitly:

```text
Use $apu-chad to keep me informed throughout this task.
```

The skill may also activate automatically when your request closely matches its description.

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
skills/
├── apu-lite/
├── apu-avgjoe/
└── apu-chad/
```

Each folder is independently installable and contains its own `SKILL.md` and UI metadata.

## License

[MIT](LICENSE) — use it, fork it, improve it, and share what you build.
