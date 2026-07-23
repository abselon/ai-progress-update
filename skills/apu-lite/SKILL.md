---
name: apu-lite
description: Produce compact, truthful AI progress updates in one or two lines. Use when the user asks for APU Lite, a quick status, a lightweight checkpoint, a concise completion percentage, or unobtrusive progress reporting during a task.
---

# APU Lite

Give the user a fast progress pulse without interrupting the work.

## Build the update

1. Identify the current named checkpoint only when a real staged plan exists.
2. Count only confirmed completed units. Keep the same denominator as the previous update unless scope genuinely changes.
3. Compute `overall = completed / total * 100`. Round to the nearest whole percent unless precision matters.
4. Choose one honest state: `On track`, `At risk`, `Blocked`, or `Complete`.
5. Name the immediate next action in a few words.

Use this default form:

```text
APU Lite — Checkpoint {current}/{checkpoints}: {name} | Total {done}/{total} ({percent}%) | {state} | Next: {action}
```

Example:

```text
APU Lite — Checkpoint 12/14: Auth Hardening | Total 19/20 (95%) | On track | Next: verify token rotation
```

If no reliable denominator exists, do not invent one:

```text
APU Lite — Auth Hardening | In progress | Scope not yet bounded | Next: inventory remaining auth paths
```

## Keep it honest

- Treat `Checkpoint 12/14` as position in a real staged plan, and `Total 19/20` as completed work units. Do not blur the two.
- Count verified outcomes, not effort, elapsed time, tool calls, or files merely opened.
- Never increase the percentage because the task feels close.
- If scope changes, say `Scope revised: 19/20 -> 19/23` before using the new denominator.
- Preserve blockers and uncertainty even when they make the update less impressive.
- Omit unavailable fields instead of filling them with guesses.
- Do not estimate time unless the user asks and there is a defensible basis.

## Control cadence

Send an update when the user asks, when a meaningful checkpoint changes, before a genuine wait, or when a blocker appears. Do not repeat an unchanged update. Continue the task immediately after an intermediate update.

At completion, report `Complete` only after the requested result and proportionate verification are finished.
