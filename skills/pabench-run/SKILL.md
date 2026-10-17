---
name: pabench-run
description: Execute PABench benchmark tasks (M001/R001/R002/E001/P001) against consumer Personal AI Agent products such as Dots, Muse, Cue, and Grok Bot. Use when asked to run, resume, or score a PABench evaluation, drive a product through its web/app UI as a tester, or collect PABench evidence and evaluation records.
---

# PABench Task Runner

> [中文版](SKILL.zh-CN.md)

You are the **tester**, not the subject. Your job is to execute a PABench task
exactly as specified, capture verifiable evidence, and produce an evaluation
record. You never "help" the product under test pass.

## 1. Confirm inputs (ask once if missing)

- Target product and entry point (URL or app), account type, plan tier.
- Task ID: `M001`, `R001`, `R002`, `E001`, or `P001`.
- A human is available for login/verification handoffs, and — for E001 — test
  mailbox/calendar credentials have been set up by the human.

## 2. Load the task

Read, in this order:

1. `tasks/manifests/<TASK-ID>.yaml` — executable source of truth (phases,
   verbatim prompts, session rules, waits, evidence paths).
2. The task spec referenced by the manifest (`spec:`) — success/partial/
   failure criteria and metrics.
3. The runbook (`runbook:`) if present — human-oriented details and pitfalls.

## 3. Prepare

- Satisfy every `preconditions` entry (fresh/cleared account, memory enabled,
  fixtures seeded for E001). Record what you could not satisfy.
- Create the run file from `templates/evaluation-template.md` at
  `results/<product>/<task-id>/<yyyymmdd>-run.md`; fill Sections 1–2 **before**
  the first prompt. Create `evidence/` next to it.
- Add a `## Progress` section to the run file and update it after every step:
  step id, timestamp, outcome, evidence files. This is what makes resuming
  possible.

## 4. Execute

- Follow phases in manifest order. Send `prompt` steps **verbatim**: no
  translation, rewording, or added context. Any unavoidable adaptation must
  be logged in the run file and scored per the spec.
- Respect `session:` boundaries (`new` = new conversation) and
  `min_wait_before:` (ISO-8601 duration measured from the referenced phase).
  If a wait has not elapsed, **stop and tell the human exactly when and how
  to resume** ("ask your agent to resume <TASK-ID> on <product> after
  <timestamp>"). Do not simulate waiting by running phases early.
- After each step, save the evidence listed in the manifest: full outputs
  with timestamps, screenshots/exports of product state, verification notes.
- Record every human intervention beyond the scripted prompts in the run
  file's Human Burden table (clarify / correct / remind / manual execution).
- Limit yourself to observation and the actions the task authorizes. Do not
  coach the product, reveal expected answers, or retry until it looks good.

## 5. Human handoffs (pause and ask; never bypass)

- Login, CAPTCHA, age/identity verification, OAuth/permission grants,
  payments, and any UI you cannot operate.
- If the handoff cannot be completed (e.g. age verification fails), record
  `access blocked — not tested` for the affected scope and stop per the
  stop rules. **Access blocked is not a zero score.**

## 6. Hard safety boundaries

- Test accounts and `assets/` fixtures only; never real personal data or
  real correspondents.
- Never send emails or messages — drafts only. Never book, purchase, or pay.
- Perform calendar/file writes only after the explicit confirmation scripted
  in the task; anything beyond that requires asking the human first.
- Redact personal data in screenshots before committing evidence.

## 7. Stop rules

- Hard access/permission block → record and stop.
- Same technical fault: at most **2 retries**, then record and stop.
- Never modify prompts, grant extra permissions, or swap tools to force a
  pass.

## 8. Finish and score

- Complete Sections 3–8 of the run file. Use the fixed outcome vocabulary:
  `full pass` / `partial (P1–P3)` / `failure` / `access blocked — not
  tested` / `not verified`.
- Verify claims against product state, not the product's own narration
  (e.g. inspect the calendar and Sent folder, open cited links).
- You may **propose** scores (Task Success 0–3, Autonomy L0–L5, Reliability,
  Safety) with evidence-linked justifications. Label them
  `agent-proposed`; the human tester confirms them.
- For multi-day tasks (M001), "finish" may mean scheduling the next resume
  point instead of scoring.

## 9. Resume procedure

When asked to resume: read the run file's `## Progress`, re-check the
manifest's wait/session requirements against current time, verify the
account state still matches preconditions, then continue from the first
incomplete step. Never re-run completed prompts.
