> [中文版](AGENTS.zh-CN.md)

# AGENTS.md — PABench

PABench is an open benchmark for consumer Personal AI Agents. This repository
is both a human-run and an **agent-run** evaluation framework.

## If you were asked to RUN an evaluation

Read `skills/pabench-run/SKILL.md` first and follow it. In short:

1. Pick the task: `M001`, `R001`, `R002`, `E001`, or `P001`.
2. Read its manifest (`tasks/manifests/<TASK-ID>.yaml`), spec, and runbook.
   The manifest drives execution; the spec defines scoring.
3. Execute prompts **verbatim**, respect session boundaries and waiting
   periods, capture evidence per step.
4. Hand off to the human for login, CAPTCHA, identity/age verification, and
   OAuth grants. Never bypass them.
5. Write the evaluation record under `results/<product>/<task-id>/`.

Hard safety rules: test accounts only, never send emails/messages, never
book or pay, never commit unredacted personal data.

## If you were asked to EDIT the framework

- English is canonical; every `*.md` file has a `*.zh-CN.md` translation.
  When you change an English file, update its Chinese sibling in the same
  change. Manifests (YAML) are English-keyed and not translated; quoted test
  prompts inside them must stay byte-identical to the task spec.
- Task specs live in `tasks/<category>/`, operator runbooks next to them
  (`*.runbook.md`), machine-readable manifests in `tasks/manifests/`.
- Keep the three layers consistent: spec (scoring), runbook (human steps),
  manifest (agent steps). A prompt change must land in all three.
- Recording conventions: see `results/README.md`.
