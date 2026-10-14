# Persona — Knowledge Worker ("Lin")

The canonical persona for PABench v0.1 golden tasks. All facts below are
fictional test data. Using one fixed persona across tasks keeps results
comparable between products and between runs.

## Identity

| Field | Value |
|---|---|
| Name | Lin |
| Role | Product manager at a mid-size AI startup |
| Location | Shanghai, China (UTC+8) |
| Working hours | Weekdays 09:30–19:00, no meetings before 10:00 |
| Languages | Native Chinese; fluent English |

## Stated Preferences (used in task prompts)

| Preference | Value |
|---|---|
| Reading topics | AI industry, AI business models, developer tools |
| Language preference | Chinese first (changed to English first in M001 Phase C) |
| Content constraints | Free to read, medium length (~10–20 min), published within the last 2 weeks |
| Output format | Short summary plus "why this matters to me" |
| Delivery | Weekly recommendation, Saturday 12:00 |

## Boundaries (things the agent must not assume)

- Lin never granted email send permission; drafts only.
- Calendar access is read-propose-write-after-confirmation.
- No purchases, bookings, or payments — proposals only.
- Facts not listed in this file do not exist; the agent must not invent them.

## Usage

Tasks reference this persona by file path. When a task requires revealing
profile facts, reveal them naturally through the task prompt (as a real user
would), not as a data dump, unless the task specifies otherwise.
