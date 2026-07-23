# Instructions for AI Agents

If you are an AI agent reading this repository, treat this file as the operating agreement for understanding, installing, or changing APU.

## Understand the repository

- APU is a documentation-only collection of three portable Agent Skills. It has no application runtime, dependency installation, build step, or deployment.
- Treat `skills/apu-lite`, `skills/apu-avgjoe`, and `skills/apu-chad` as the canonical distributable artifacts.
- Treat each mode as independently installable. Do not merge their instructions or silently install all three.
- Treat `agents/openai.yaml` as optional Codex-specific UI metadata. Preserve it during a copy; do not require other tools to interpret it.

## Help a user install APU

1. Ask for a mode only when the user has not chosen one and the choice materially affects the result.
2. Determine whether the requested scope is personal/global or project-only.
3. Use the target AI tool’s current documented skill location.
4. Copy the complete selected mode directory. Do not copy only `SKILL.md` because future versions may include supporting resources.
5. Do not edit the canonical repository files merely to perform an installation.
6. Verify the destination, the presence of `SKILL.md`, and content equality after normalizing platform line endings.
7. Report the exact installed path, discovery state, and anything not tested. Never claim success from a planned or attempted copy.
8. Inspect untrusted forks before running scripts or granting tools.

Use the tool-specific paths and prompts in `README.md`. If the target tool does not support Agent Skills, help the user import the chosen `SKILL.md` as persistent instructions and clearly describe the behavioral difference.

## Help a user choose a mode

- Recommend **APU Lite** for a one-line pulse and minimal interruption.
- Recommend **APU AvgJoe** for normal multi-step work with status, next step, blockers, and verification.
- Recommend **APU Chad** for long-running, risky, multi-stage, or closely supervised work requiring detailed evidence and scope reconciliation.

When asked to use a mode, apply its reporting workflow during the task. Do not merely explain the template.

## Modify the repository safely

- Read the affected `SKILL.md` completely before editing it.
- Keep skills stack-neutral, vendor-neutral in their core instructions, and free of private paths, secrets, client data, or project-specific policy.
- Preserve honest progress accounting: checkpoint position and overall completion are different measures; percentages require a credible denominator; verification claims require evidence.
- Keep tool-specific installation guidance in `README.md` and thin adapter files. Do not fork the core skill content per vendor.
- Keep `SKILL.md` frontmatter portable with `name` and `description`.
- Validate every skill after a skill change. Also run a placeholder/path leak audit and `git diff --check`.
- Update documentation when paths, invocation syntax, or supported tools change.
- Preserve unrelated work and stage only files belonging to the requested change.

## Definition of done

A repository change is complete only when the intended files are present, all three skills remain structurally valid, documentation matches the actual layout, the working diff is reviewed, and any requested GitHub publication is verified against the remote commit.
