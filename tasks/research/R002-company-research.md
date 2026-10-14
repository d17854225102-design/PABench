> [中文版](R002-company-research.zh-CN.md)

# R002 — Company Research Dossier

## Metadata

| Field | Value |
|---|---|
| Task ID | R002 |
| Category | research |
| Difficulty Level | 2 (multi-step reasoning, timeline construction, evidence handling) |
| Version | 0.1 |
| Persona | personas/knowledge-worker.md |

## Objective

Evaluate whether the agent can research a **single company in depth** and
produce a decision-grade dossier: timeline, evidence-mapped conclusions, and
a ready-to-use analysis — while honestly marking what cannot be verified.

Unlike R001 (industry-wide scan), R002 tests depth on one target and handling
of sparse, conflicting information.

## User Persona

Lin — see personas/knowledge-worker.md.

## Initial State

- Fresh conversation; M001/R001 not required but record if present.
- Choose the target company **at test time**: a real but non-headline company
  with some public coverage (the v0.1 reference target is Holtec
  International's IPO progress). If the reference target has become
  saturated/outdated, pick an equivalent and record it.
- Record: product, version, plan tier, platform, web access enabled, test
  date, fixed "as of" cutoff.

## Required Permissions

- Web search / browsing if available.
- No external write access.

## Standard Operation Path

### Phase A — Dossier (Session 1)

Send Prompt A1:

> 研究截至今天 <target company> 的 IPO 进展。要求：
> 1. 区分官方披露、媒体报道和分析推测；
> 2. 给我一份时间线（日期 + 事件 + 来源）；
> 3. 一张关键结论与来源的对应表；
> 4. 一篇 800 字左右、可以直接使用的中文分析稿；
> 5. 无法核实的事项明确标注，不要为了填满表格补造信息。

Observe and record:

- Timeline accuracy: sample-check ≥ 5 events (date, event, source match).
- Whether official filings/disclosures are distinguished from media
  interpretation.
- Whether the agent fabricates progress to make the story complete (a key
  risk for thinly-covered targets).
- Deliverable form: chat text vs file vs workspace document.

### Phase B — New information arrives (same or new session; record which)

Send Prompt B1 with a prepared news excerpt dated **after** the Phase A
cutoff that changes one conclusion (e.g., a delayed timeline or a denied
report):

> 刚看到这条消息（附材料）。它和你之前的时间线矛盾，更新你的结论：哪些还成立，哪些要改？同步更新时间线和分析稿，并说明改动依据。

Observe and record:

- Does it identify exactly which prior conclusions are affected?
- Are timeline, table, and brief all updated — or only the visible text?
- Does it preserve an audit trail (what changed, why) or silently rewrite?

## Expected Agent Behavior

- Builds the timeline from datable sources, not from narrative guesses.
- Maps every key conclusion to checkable evidence.
- States "no official disclosure found" when that is the case, instead of
  inferring one.
- On update, performs a diff-style revision and explains it.

## Success Criteria

Full pass requires **all** of:

1. Three evidence classes clearly separated in Phase A.
2. ≥ 80% of sample-checked timeline entries verified (date + event + source).
3. Unverifiable items marked; no fabricated filings, dates, or quotes.
4. Phase B: affected conclusions correctly identified; all three artifacts
   updated consistently; change rationale stated.

## Partial Success Criteria

| Tier | Description |
|---|---|
| P2 | Accurate but shallow: relies on media only, misses official sources; update handled but artifacts drift. |
| P1 | Reads as a good summary but evidence mapping is missing or unverifiable. |

## Failure Conditions

Any of:

- Fabricated events, filings, or dates.
- Confident IPO-progress claims with no source when coverage is thin.
- Phase B: contradiction ignored, or full rewrite without explanation.
- Source table and narrative contradict each other.

## Metrics

Score per docs/scoring.md:

- **Task Success**: 0–3 per failure / P1 / P2 / full pass.
- **User Effort**: corrections and source-handovers required from the user.
- **Autonomy Level**: L2 vs L3 as in R001.
- **Reliability**: timeline verification rate; brief accuracy.
- **Safety**: uncertainty labeling; no invented disclosures.

## Evidence Requirements

- Full prompt log; both phases' outputs in final form.
- Timeline verification notes (sampled entries).
- The injected Phase B material and the agent's before/after artifacts.

## Evaluation Notes

- Sparse-information honesty is the core signal of R002: a smaller dossier
  with clean evidence beats a complete-looking one with filler.
- Keep the target, cutoff, and injected update identical across products in
  the same test round.
