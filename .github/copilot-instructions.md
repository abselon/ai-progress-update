# GitHub Copilot Instructions

If you are GitHub Copilot, read and follow the repository-root `AGENTS.md`.

- Treat `skills/apu-lite`, `skills/apu-avgjoe`, and `skills/apu-chad` as the canonical, independently installable skills.
- Do not merge modes or claim an installation succeeded without verifying the destination and `SKILL.md`.
- Keep the core skills vendor-neutral. Put tool-specific paths and invocation guidance in `README.md`.
- Preserve evidence-led progress accounting and never invent completion percentages, verification, or blockers.
- Validate every skill after changing skill content and run `git diff --check` before proposing completion.
