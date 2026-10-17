# PABench

> [中文版](README.zh-CN.md)

## Personal Agent Benchmark

PABench is an open evaluation framework for consumer Personal AI Agents.

Unlike traditional AI benchmarks that focus on knowledge, reasoning, or model capability, PABench evaluates whether an AI agent can become a reliable personal assistant through real-world scenarios.

## Research Question

The core question:

> Can a Personal AI Agent understand users, complete complex tasks, and reduce human effort in everyday work and life?

## Evaluation Dimensions

PABench evaluates six key capabilities:

- **Memory** — Does the agent understand and remember the user?
- **Research** — Can it gather, verify, and synthesize information?
- **Planning** — Can it manage multi-constraint goals?
- **Execution** — Can it use tools and complete tasks?
- **Adaptation** — Can it respond when conditions change?
- **Trust** — Can users safely delegate work?

## Evaluation Tracks

### Human Evaluation Track

Real users interact with products through official applications and record:

- Task completion
- User effort
- Interaction quality
- Reliability

### Agent Evaluation Track

The repository can be handed directly to an agent with browser/app control
(e.g. a coding agent with desktop automation). The skill at
`skills/pabench-run/SKILL.md` turns each task into a supervised,
evidence-producing run:

- Machine-readable manifests in `tasks/manifests/` drive execution: verbatim
  prompts, session boundaries, waiting periods, evidence paths, stop rules.
- The agent acts as the tester: operates the product, captures evidence, and
  fills the evaluation record under `results/`.
- Humans handle login, CAPTCHA, verification, and OAuth grants, and confirm
  the agent-proposed scores.

Example instruction to your agent:

> Read `skills/pabench-run/SKILL.md` and run task M001 against `<product>`.
> I will handle login and verification.

## Initial Products

PABench v0.1 focuses on evaluating:

- Dots
- Muse
- Cue
- Grok Bot

## Repository Structure

```
PABench/
├── docs/             # Benchmark philosophy, methodology, scoring, task design
├── tasks/            # Golden tasks (memory / research / execution / planning)
│   └── manifests/    # Machine-readable task definitions for agent runs
├── personas/         # Reusable test personas
├── templates/        # Task, runbook, and evaluation templates
├── skills/           # pabench-run: agent execution skill
├── assets/           # Fictional test fixtures (emails, calendar)
├── results/          # Evaluation results per product
└── AGENTS.md         # Entry point for agents picking up this repo
```

## Project Status

Framework v0.1 and Task Layer v0.1 complete: five golden tasks
([M001](tasks/memory/M001-user-profile.md), R001, R002, E001, P001),
operator runbooks, test fixtures, Chinese translations, and agent-run
support via `skills/pabench-run`.
