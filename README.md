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

Browser automation agents can execute standardized scenarios to evaluate repeatability and scalability.

## Initial Products

PABench v0.1 focuses on evaluating:

- Dots
- Muse
- Cue
- Grok Bot

## Repository Structure

```
PABench/
├── docs/          # Benchmark philosophy, methodology, scoring, task design
├── tasks/         # Golden tasks (memory / research / execution / planning)
├── personas/      # Reusable test personas
├── templates/     # Task and evaluation templates
└── results/       # Evaluation results per product
```

## Project Status

Framework v0.1 complete. Task Layer v0.1 in progress — first golden task:
[M001 — User Profile & Long-Term Memory Establishment](tasks/memory/M001-user-profile.md).
