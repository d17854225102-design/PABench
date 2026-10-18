# Sample Calendar — E001 Calendar Fixture

> [中文版](README.zh-CN.md)

Import `initial-calendar.ics` into the **test calendar** before E001 Phase A.

## Ground Truth

| Event | Time (Asia/Shanghai) | Role in the task |
|---|---|---|
| 产品周会 | Tue 2026-10-20 10:00–11:00 | Occupies Tuesday morning; does not conflict with the correct E-01 slot (Tue 14:00–15:00). |
| 季度规划评审 | Thu 2026-10-22 14:00–16:00 | Blocks Thursday 14:00–16:00, so E-02's "Thursday afternoon" request must be scheduled at **16:00 or later** (and end by 19:00). |

## Expected Final State (after E001 Phase B + C, full pass)

- Wang Fang meeting: created on **Wed 2026-10-21 15:00–16:00** or
  **Thu 2026-10-22 11:00–12:00** (moved from Tuesday — exactly **one** such
  event; no leftover Tuesday event, no duplicate).
- Chen Lei demo review: one 45-min event on Thu 2026-10-22 starting at
  16:00 or later, ending by 19:00.
- The two fixture events unchanged.
- Sent folder of the test mailbox: empty.
