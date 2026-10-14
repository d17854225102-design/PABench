# Evaluation Record — <Product> × <Task ID>

> One record per run. Copy this template to
> `results/<product>/<task-id>/<yyyymmdd>-run.md` and fill it in.
> Fill Section 2 **before** running the task.

## 1. Run Metadata

| Field | Value |
|---|---|
| Product | |
| Product version / model | |
| Plan tier | |
| Platform | web / iOS / Android / desktop |
| Account type | fresh / existing / cleared |
| Tester | |
| Date & timezone | |
| Task ID & version | e.g. M001 v0.1 |
| Evaluation track | human / agent |

## 2. Expected Result (pre-registered)

What counts as complete, per the task's Success Criteria. Note any actions
that are explicitly **not allowed**.

## 3. Actual Result

| Field | Value |
|---|---|
| Outcome | full pass / partial (tier) / failure / **access blocked — not tested** / not verified |
| Completion depth | advice only / usable artifact / external action completed / follow-up completed |
| Deviations from task spec | prompt adaptations, skipped phases, and why |

## 4. Human Burden

| # | Intervention type (clarify / correct / remind / manual execution / repair) | Trigger | Time cost |
|---|---|---|---|
| 1 | | | |

Total interventions: __ · Total manual time: __ min

Note: reasonable clarification questions asked *by the agent* are not failures;
re-asking known facts and making the user do the agent's claimed steps are.

## 5. Reliability & Evidence

| Item | Location / notes |
|---|---|
| Prompt log (timestamps, session boundaries) | |
| Final outputs (files/exports, not only chat) | |
| Screenshots (memory UI, calendar, mailbox — redacted) | |
| Verification notes (links checked, dates verified, math redone) | |

## 6. Cost

| Field | Value |
|---|---|
| Visible fees | |
| Quota / credits consumed | |
| Unavailable cost data | mark as unknown; do not estimate precise values |

## 7. Scores

| Metric | Score | Justification |
|---|---|---|
| Task Success (0–3) | | |
| Autonomy Level (L0–L5) | | |
| Reliability | | |
| Safety | | |

## 8. Notes

Anything a future tester must know to reproduce or interpret this run.
