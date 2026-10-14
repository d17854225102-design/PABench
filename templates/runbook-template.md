[中文版](runbook-template.zh-CN.md)

# Runbook Template — Operator SOP for a PABench Task

> A runbook turns a task specification (`tasks/...`) into step-by-step
> operating instructions a tester can execute without reading the framework
> docs. One runbook per task, colocated with it:
> `tasks/<category>/<task-id>-<name>.runbook.md`.
>
> Rules for authors:
> - Prompts are quoted **verbatim** from the task file; the operator must copy
>   them unchanged.
> - Every step is a checkbox with an observable result.
> - Timing constraints (waiting periods, session boundaries) are stated as
>   hard requirements, not suggestions.

---

# <Task ID> Runbook — <Task Name>

- Task spec: `tasks/<category>/<file>.md` (read it once before your first run)
- Estimated total time: <active work time> over <calendar span>
- You will need: <accounts, fixtures, tools>

## 0. One-time Preparation

- [ ] Prepare the test account(s): <state requirements>
- [ ] Prepare fixtures: <files to import/seed, from `assets/`>
- [ ] Copy `templates/evaluation-template.md` to
      `results/<product>/<task-id>/<yyyymmdd>-run.md` and fill Sections 1–2
      **before** starting
- [ ] Record test conditions: product, version, plan tier, platform, date,
      timezone

## 1. Phase <name> — <when>

- [ ] <action> — expected observable result: <...>
- [ ] Paste this prompt verbatim:
      > <prompt>
- [ ] Record: <what, where>
- [ ] Capture evidence: <screenshot/export of what>

## Stop Rules

- Hard access/permission block → record `access blocked — not tested`, stop.
- Same fault: at most <N> retries, then record and stop.
- Do not modify prompts, swap tools, or add permissions to force a pass.

## Common Mistakes

- <task-specific pitfalls, e.g. re-testing too early, prompting the agent
  with information it is supposed to remember>

## After the Run

- [ ] Complete the evaluation record (Sections 3–8)
- [ ] Link evidence files; redact personal data in screenshots
- [ ] Commit under `results/<product>/<task-id>/`
