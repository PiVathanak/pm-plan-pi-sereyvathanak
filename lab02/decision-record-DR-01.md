# DR-01 · Open-day demo scope, week 10

**Status:** approved
**Date:** 2026-10-24
**Requested by:** Head of IT (sponsor)

## Context

The sponsor asked for every Should feature (F09-F12) to be finished by
week 10 for the department open day, with the week-14 pilot unchanged.
Fixed facts:

- C-01: pilot with 50 students at week 14 stays.
- C-02: team capacity is 40 h/week, so 240 h for W5-W10.
- C-03: Must scope is 300 h, 148 h done after two sprints, 152 h remain.
- C-04: Should scope is 86 h (F09 20, F10 30, F11 24, F12 12).
- C-05: contingency is 56 h.

Needed by W10 = 152 + 86 = 238 h against 240 h capacity: a 2 h
surplus with 0 h contingency used, and 54 h (1.35 weeks) with contingency
intact. Velocity of sprints 1-2 was 18 and 21 points (19.5 average).

## Options considered

| Option                | Scope at W10                                | Time (W5-W10)  | Cost / buffer                   | Quality                                           |
| --------------------- | ------------------------------------------- | -------------- | ------------------------------- | ------------------------------------------------- |
| A. All Should by W10  | Must + F09-F12                              | 238 h vs 240 h | 2 h buffer, 0 h contingency     | Feasible but leaves no risk buffer                |
| B. Counter-proposal 1 | Must + Responsive (20 h) + Analytics (30 h) | 202 h          | 38 h buffer (18 h below policy) | Real features, real data                          |
| C. Counter-proposal 2 | Must + mocked analytics demo (8 h)          | 160 h          | 80 h buffer                     | Fake analytics data at open day, 8 h not reusable |

## Decision

Counter-proposal 1 (option B). F09 and F10 move to the W10 demo
milestone. F11, F12 and F13 stay at the W14 pilot. No Could work before W11.

## Consequences

- New milestone "Open day demo" at W10 in the schedule baseline.
- New Won't items for the W10 build: Export (F11) and Notifications (F12)
  are Won't until W14; existing Won't F17 remains deferred; Could work waits
  until W11.
- R-10: demo on unfinished analytics. Trigger: Analytics more than 10 h
  behind at end of W9; response: switch to mocked analytics (8 h).
- R-11: buffer of 38 h is below the 56 h contingency (C-05). Mitigation:
  weekly remaining-hours report to the sponsor every Friday.
- Pilot date (C-01) unchanged; baseline and schedule updated by W5.

## Approvers

- Head of IT (sponsor)
- Project manager, Team 2
