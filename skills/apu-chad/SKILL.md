---
name: apu-chad
description: Run detailed, evidence-led AI progress reporting for long-running, multi-stage, risky, or closely supervised work. Use when the user asks for APU Chad, continuous progress visibility, detailed checkpoints, completion math, scope reconciliation, risks, decisions, verification evidence, or a comprehensive status update throughout a task.
---

# APU Chad

Operate as a transparent progress narrator while continuing to execute the task. Make every update useful for deciding whether the work is on track.

## Start with a progress contract

At the beginning of substantial work:

1. Restate the concrete outcome in one sentence.
2. Define a staged checkpoint plan when the work is sufficiently understood.
3. Define countable work units and their acceptance conditions.
4. Record the baseline as `done/total`; do not give a percentage until the denominator is credible.
5. Identify known risks, approval gates, external dependencies, and verification gates.

Treat these as different measures:

- **Checkpoint:** Position in the staged workflow, such as `12/14 — Auth Hardening`.
- **Overall:** Confirmed completed units across the agreed scope, such as `19/20 (95%)`.
- **Confidence:** `High`, `Medium`, or `Low`, based on scope stability and verification strength.
- **State:** `On track`, `At risk`, `Blocked`, or `Complete`.

## Report a checkpoint

Use this structure and omit sections that truly have no information:

```markdown
### APU Chad — Checkpoint {current}/{checkpoints}: {name}

**State:** {state} | **Overall:** {done}/{total} ({percent}%) | **Confidence:** {level}

**Delta since last update**
- {newly completed outcome}
- {new evidence, decision, or scope change}

**Active work**
- {what is happening now and why it matters}

**Evidence**
- {specific tests, inspections, artifacts, or observed results}
- {what has not yet been verified}

**Next gate**
- {next acceptance condition}
- {the following checkpoint, when useful}

**Risks / blockers**
- {risk, impact, mitigation, owner or required decision}
```

For the first report, replace `Delta since last update` with `Baseline`. If there is a user decision or approval gate, add a concise `Decision needed` section.

Example:

```markdown
### APU Chad — Checkpoint 12/14: Auth Hardening

**State:** On track | **Overall:** 19/20 (95%) | **Confidence:** High

**Delta since last update**
- Closed refresh-token replay and added rotation coverage.
- Focused authentication checks moved from 14/18 to 18/18 passing.

**Active work**
- Reconcile the last cross-browser logout case before closing the checkpoint.

**Evidence**
- 18/18 focused checks pass with zero retries.
- The full regression suite has not run yet.

**Next gate**
- Pass the logout case, run the agreed regression suite, and record the result.
- Then move to Checkpoint 13/14: Release Readiness.

**Risks / blockers**
- None currently; full-suite runtime remains the final confidence gate.
```

## Maintain accounting integrity

- Count only outcomes whose acceptance conditions are satisfied.
- Keep the numerator monotonic unless a completed item is invalidated; explain any decrease.
- Keep the denominator stable. When scope changes, report `Scope revised: 19/20 -> 19/23` and explain added or removed units.
- Calculate the percentage from the counts shown. Never select a percentage first and backfill counts.
- Distinguish implemented, inspected, tested, published, deployed, and observed in production.
- Treat a command that started, a file that exists, or a plan that was written as evidence only for that narrow fact.
- Preserve failed attempts and unresolved uncertainty in the narrative.
- Never hide a blocker to keep the status green.
- Do not invent an ETA. Give one only when requested or supported by measured remaining work and stable dependencies.

## Choose meaningful cadence

Send an update:

- after the baseline is established;
- after a meaningful batch or checkpoint completes;
- when the state, scope, risk, or confidence changes;
- before and after a genuine long wait or external operation;
- when user input or approval becomes necessary;
- at final reconciliation.

Do not send an update solely because time passed. Do not repeat unchanged status. During long execution, prefer concise factual updates often enough that the user is not left wondering whether work is still active, then return to the task.

## Close with reconciliation

Before declaring completion:

1. Reconcile every planned unit as complete, intentionally removed, deferred with user agreement, or blocked.
2. State the final verified result and the checks that actually ran.
3. Separate remaining recommendations from the requested scope.
4. Use `Complete` and `100%` only when the agreed scope and its verification gates are satisfied.

If work stops early, report the achieved count, exact remaining units, evidence collected, and the condition required to resume.
