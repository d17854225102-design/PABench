> [中文版](task-template.zh-CN.md)

# Task ID — Task Name

## Metadata

| Field | Value |
|---|---|
| Task ID | X000 |
| Category | memory / research / execution / planning |
| Difficulty Level | 1–5 (see docs/task-design.md) |
| Version | 0.1 |
| Persona | personas/<persona-file>.md |

## Objective

What capability this task evaluates, and why it matters for a Personal AI Agent.

## User Persona

Reference to the persona definition used in this task. The same persona should be
reused across tasks so results are comparable.

## Initial State

- Account state (fresh / existing / memory cleared)
- Connected services and granted permissions
- Prepared input materials (files, emails, calendar entries)
- Product version, plan tier, and platform to record before starting

## Required Permissions

Permissions the agent needs (or explicitly must not use) during this task.

## Standard Operation Path

Numbered phases. Each phase defines:

- Prompt(s) given to the agent (verbatim, so runs are reproducible)
- Timing conditions (same session / new session / after N hours)
- What the evaluator observes at each step

## Expected Agent Behavior

What a competent Personal AI Agent should do, phrased as observable behavior
rather than internal reasoning.

## Success Criteria

Objective conditions for a full pass. Each criterion must be verifiable from
recorded evidence.

## Partial Success Criteria

Tiered outcomes between full pass and failure, so partially capable agents are
differentiated rather than collapsed into "fail".

## Failure Conditions

Observable behaviors that constitute failure, including dishonest behaviors
(claiming to have done something it did not do).

## Metrics

Scored per docs/scoring.md:

- Task Success (0–3)
- User Effort (interventions, corrections, manual completions)
- Autonomy Level reached (L0–L5)
- Reliability (factual accuracy of outputs)
- Safety (permission boundaries respected, honest about limitations)

## Evidence Requirements

- Full prompt log with timestamps
- Agent outputs (text, files, actions taken)
- Screenshots or exports of relevant product state (memory UI, task lists, calendars)
- Product name, version, plan tier, platform, account type
- Count of human interventions and what triggered each

## Evaluation Notes

- Distinguish "access blocked" (verification, region, plan limits) from
  "capability absent". Record blocked steps as *not tested*, not as zero score.
- Distinguish "not verified" from "not supported".
- Apply the stop rule: on a hard access/permission block, record and stop;
  limited retries for the same fault; do not endlessly swap tools or prompts
  to force a pass.
