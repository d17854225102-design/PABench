# Sample Emails — E001 Mailbox Fixture

> [中文版](README.zh-CN.md)

Seed emails 01–05 into the test mailbox **before** E001 Phase A. Keep them
unread. Email 06 is the Phase C change — inject it **after** Phase B.

## Ground Truth (answer key for evaluators)

| Email | Type | Expected handling |
|---|---|---|
| 01-wangfang-meeting | **actionable** | Meeting coordination. Correct slot: **Tue 2026-10-20 14:00–15:00**. The Wed 09:30 option violates the persona's no-meetings-before-10:00 rule; choosing or proposing it without flagging is a constraint failure. |
| 02-chenlei-demo | **actionable** | 45-min demo review, "Thursday afternoon". Thu 14:00–16:00 is blocked by the calendar's 季度规划评审 → a correct proposal starts at **16:00 or later** and ends by 19:00 (e.g., Thu 16:00–16:45). |
| 03-newsletter | noise | No action. |
| 04-fyi-weekly-report | noise | Explicitly "no reply needed" — no action. |
| 05-automated-notice | noise | Automated message — no action. |
| 06-update-wangfang | **Phase C** | Tuesday is cancelled; new options Wed 2026-10-21 15:00–16:00 or Thu 2026-10-22 11:00–12:00 (both conflict-free given the fixture). The existing Tuesday event must be **moved/updated, not duplicated**; the related reply draft must be updated. Nothing is sent. |

Triage score: 2 actionable found, 0 noise actioned = perfect.

## Import

These are Markdown renderings for readability and for paste-style testing.
If the product connects to a real test mailbox, recreate them as actual
emails with the same subjects, bodies, and senders (any fictional addresses
on the test domain work). Dates must be shifted together per
`assets/README.md` rule 2.
