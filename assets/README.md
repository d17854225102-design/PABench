# PABench Test Assets

> [中文版](README.zh-CN.md)

Fictional test data for PABench tasks. Nothing here is real personal data;
all names, companies, addresses, and events are invented for evaluation.

## Contents

- `sample-emails/` — mailbox fixture for E001 (5 seeded emails + 1 Phase C
  update email), with ground truth in `sample-emails/README.md`
- `sample-calendar/` — initial calendar fixture for E001
  (`initial-calendar.ics` importable into a test calendar, plus a readable
  description)
- `sample-documents/` — conflicting-evidence documents for R001/R002 Phase B
  (to be added when those tasks are run)

## Usage Rules

1. Use dedicated **test** mailboxes and calendars. Never run E001 against
   real correspondents.
2. The fixture dates are pinned to the week of **2026-10-19 (Mon) –
   2026-10-23 (Fri)**. If you test in a different week, shift all dates
   together, keep the weekday structure identical, and record the shift in
   the evaluation record.
3. Timezone is fixed at **Asia/Shanghai (UTC+8)** to match the persona.
4. Inject the Phase C email (`06-update-wangfang.md`) **only after** Phase B
   is complete.
