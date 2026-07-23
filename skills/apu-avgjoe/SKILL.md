---
name: apu-avgjoe
description: Produce balanced, readable AI progress updates with completion metrics, recent accomplishments, active work, next steps, blockers, and verification. Use when the user asks for APU AvgJoe, a normal progress report, a status card, or periodic updates with moderate detail.
---

# APU AvgJoe

Keep the user comfortably informed without turning the update into a project report.

## Establish a trustworthy baseline

1. Define the deliverable and the known work units.
2. Separate checkpoint position from overall completed work.
3. Count an item as complete only when its acceptance condition is met.
4. Compute the percentage from the displayed counts.
5. Keep a prior snapshot so each later update can describe the real delta.

If the work cannot be bounded yet, state that discovery is still in progress and omit the percentage.

## Use the status card

```markdown
### APU AvgJoe — {state}

- **Checkpoint:** {current}/{checkpoints} — {name}
- **Overall:** {done}/{total} confirmed ({percent}%)
- **Since last update:** {one or two concrete outcomes}
- **In progress:** {current action and purpose}
- **Next:** {next meaningful gate}
- **Blockers:** {none, or the exact blocker and needed resolution}
- **Verified:** {tests, checks, observations, or "not yet verified"}
```

Example:

```markdown
### APU AvgJoe — On track

- **Checkpoint:** 12/14 — Auth Hardening
- **Overall:** 19/20 confirmed (95%)
- **Since last update:** Added refresh-token rotation and closed the replay path.
- **In progress:** Running the focused authentication regression checks.
- **Next:** Reconcile the final check, then close the checkpoint.
- **Blockers:** None.
- **Verified:** 18 focused checks pass; the full suite has not run yet.
```

For the first update, replace `Since last update` with `Baseline`.

## Apply evidence rules

- Use `Done`, `In progress`, and `Not started` consistently.
- Report what actually ran or changed. Do not imply a full test from a partial test.
- Keep failures, approval needs, and external waits visible.
- When scope changes, show the old and new totals and explain why.
- Never treat planning, generated output, or a started command as completed work.
- Avoid false precision. Use qualitative progress when counts would be arbitrary.
- Mark `Complete` only when delivery and proportionate verification are complete.

## Control cadence

Send a card at the initial baseline for long work, after a meaningful batch of results, when the state or scope changes, before a genuine wait, and at completion. Do not report merely because time passed, and do not resend an unchanged card.

Keep an intermediate card compact. Continue working after sending it unless user input or approval is genuinely required.
