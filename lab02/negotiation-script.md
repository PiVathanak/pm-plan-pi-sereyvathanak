# Negotiation · sponsor asks for all Should features by week 10

## Data sheet (week 4)

| Measure                                 | Value                                               |
| --------------------------------------- | --------------------------------------------------- |
| Capacity W5-W10                         | 6 x 40 = 240 h                                      |
| Must remaining (300 done 148)           | 152 h                                               |
| Should total (Task 2 rating)            | 86 h (F09 20, F10 30, F11 24, F12 12)               |
| Needed by W10 = Must remaining + Should | 152 + 86 = 238 h                                     |
| Shortfall by W10                        | 2 h surplus (0 h contingency used)                  |
| Contingency to protect                  | 56 h                                                |
| Shortfall with contingency intact       | 238 - (240 - 56) = 54 h = 1.35 weeks                |
| Velocity, sprints 1-2 (points done)     | 18, 21 -> 19.5 avg (3 sprints W5-W10 = 58.5 points) |

Needed by W10 = 152 h (Must) + 86 h (Should) = 238 h.
Capacity W5-W10 = 240 h -> 2 h surplus, with 0 h contingency used and the
Could class untouched. With contingency intact (56 h) the shortfall is
54 h = 1.35 weeks. "Everything by week 10" uses nearly all available capacity.

Fixed facts: C-01 pilot with 50 students at W14 · C-02 team capacity
40 h/week · C-03 Must = 300 h, 148 h done · C-04 Should = 86 h ·
C-05 contingency 56 h.

## Script

**Sponsor:** I need every Should feature demonstrable at the open day in
week 10. It is mostly small stuff.

**PM:** I want the open day to be a success, so let me show you what week 10
looks like in hours. The 152 h of Must work still open plus 86 h of Should
work is 238 h. Our capacity from week 5 to week 10 is 240 h. That leaves 2 h
before we keep any contingency, and 54 h short, about 1.35 weeks, once the
56 h contingency is protected.

**Sponsor:** (tactic 1: small change) But these are small changes. Export is
a button, notifications are an email. That cannot be 86 hours.

**PM:** I understand it looks that way from the screen. Our Task 2 rating
puts export at 24 h and notifications at 12 h; those two remaining
Should features total 36 h. The complete Should class is 86 h.

**Sponsor:** (tactic 2: work a bit harder) Then the team can put in some extra
evenings. Students have energy.

**PM:** Extra hours could help, and I would like to size them honestly. Closing
54 h means 1.35 weeks beyond the protected 184 h, and it would use all of the
56 h contingency, so a single slipped task of 20 h would move the week-14
pilot (C-01). Our two sprints delivered 18 and 21 points, an average of
19.5, with no overtime in them.

**Sponsor:** (tactic 3: other teams manage) Team 5 showed a full demo at their
midpoint. Other teams manage this.

**PM:** I would be glad to learn from them. To compare fairly I need their
scope in hours and their team size, because our own numbers say 3 sprints
x 19.5 = 58.5 points between W5 and W10. If you can share their figures I
will check them against ours this week.

**Sponsor:** (tactic 4: decide later) Fine. Keep everything in the plan and
we will decide in week 8 what to drop.

**PM:** That keeps options open, and it has a price. By the end of week 8 the
team will have spent 160 h on a plan that needs 238 h, so whatever we drop
then has hours already sunk into it. Deciding today costs 0 h of rework.

**Sponsor:** What if we simply push the Could features out of the plan?

**PM:** Good instinct. In the 238 h figure the Could class is already at
0 h, so moving it does not change the 2 h surplus. The protected-capacity gap sits inside Must
plus Should.

**Sponsor:** Then what can I actually have at the open day?

**PM:** Here are two ways to give you a strong open day. Option 1: finish
the Must work plus Responsive (20 h) and Analytics (30 h) by week 10.
That is 152 + 50 = 202 h of 240 h, leaving a 38 h buffer. It displaces
Export (F11) and Notifications (F12), 36 h in total, to the week-14
pilot, and Could work waits until week 11. Option 2: a demo build
with mocked analytics data for 8 h, so week 10 needs 152 + 8 = 160 h and
the buffer is 80 h. It displaces 8 h of real feature work into throwaway
mock data, and the full Should scope still lands at week 14 as planned.

**Sponsor:** How safe is option 1?

**PM:** The 38 h buffer is 18 h below our 56 h contingency policy, so I would
record it as a risk, report remaining hours to you every Friday, and
switch to option 2's mocked analytics in week 9 if Analytics is more
than 10 h behind.

**Sponsor:** I choose option 1. Real analytics on real data is what the open
day needs.

**PM:** I will record this as DR-01 today and update the baseline by W5.
DR-01 will list F09 and F10 at the W10 demo milestone, F11, F12 and F13 at
the W14 pilot, zero Could work before W11, and the new risks R-10 and
R-11. You will see the updated schedule baseline and the signed record
by the end of week 5.
