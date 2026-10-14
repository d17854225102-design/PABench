# PABench Results

Evaluation results per product. Each product directory holds one folder per
task, and each run is a single record file copied from
`templates/evaluation-template.md`.

## Layout

```
results/
├── dots/
│   └── M001/
│       ├── 20261020-run.md        # the evaluation record
│       └── evidence/              # prompt logs, screenshots (redacted), exports
├── muse/
├── cue/
└── grok/
```

## Recording Conventions

1. One file per run: `results/<product>/<task-id>/<yyyymmdd>-run.md`.
   Re-tests get new files; never overwrite history.
2. Section 2 (Expected Result) must be filled in **before** the run starts.
3. Outcomes use the fixed vocabulary: `full pass` / `partial (P1–P3)` /
   `failure` / `access blocked — not tested` / `not verified`.
4. **Access blocked ≠ capability zero.** If verification, region, or plan
   limits stop the run, record where it stopped and mark remaining
   capabilities as not tested.
5. Evidence is mandatory: link every score to files in `evidence/`. Redact
   personal data in screenshots before committing.
6. Test accounts only: never commit real email content, real contact data,
   or credentials.
