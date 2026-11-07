# TDR-01 · Life cycle and methodology for the Realtime Quiz project

Status: proposed · 2026-10-24 · to be decided by the sponsor (Head of IT) and the PM (Tal Tongsreng)

## Context

Team 3 builds the Realtime Quiz platform in 14 weeks, starting on 2026-09-29, with an MVP demo in week 7 and a pilot with 50 students in week 14. The 8 Must features are fixed in the charter, but the screens and the real-time behaviour are not specified, and live updates for many simultaneous players are new to the team. The sponsor, the data protection officer and the security team must approve the project at defined points, and IT operations hosts it on a VPS. The team has no recorded sprint practice and a lecturer acts as PM. The Task 1 profile scored 3.00, which is in the hybrid band, because stable scope and governance pull toward predictive while technical uncertainty and early feedback pull toward adaptive.

## Options considered

1. Waterfall (score 2.60): full specification first and one acceptance at the end, so real-time problems would show up too late.
2. Pure Scrum (score 3.40): fastest feedback and best on uncertainty, but no fixed approval points for the sponsor, data protection officer and security team.
3. Hybrid (score 4.00): predictive plan and four gates around four two-week sprints.

## Decision

Adopt the **Hybrid** approach (predictive plan and gates around agile sprints). First, it scored highest (4.00 against 3.40 for Scrum and 2.60 for Waterfall) and the lead survived both sensitivity tests. Second, it is the only option that gives the sponsor, data protection officer and security team fixed approval points while the sprints reduce the real-time risk and show a working quiz at the first sprint review.

## Consequences

- The sponsor approves scope, plan and four gates up front, so governance needs are met from G1.
- A playable quiz exists at the sprint 1 review (week 5), so real-time problems show up early.
- The week 7 MVP and the week 14 pilot are tied to gates G2 and G4, so they have clear acceptance evidence.
- The Must list stays baselined, so scope creep is visible at each gate.

* Gates can become paperwork and slow the sprints. -> mitigation: each gate asks for 2-3 measurable items only, and the evidence is the sprint review itself.
* A team new to sprints may run the ceremonies badly. -> mitigation: use one fixed sprint length, a short sprint review and retrospective, and let the PM coach the first two sprints.
* Fixed gate criteria may lock in decisions before the team has learned enough. -> mitigation: gate criteria are about outcomes (for example a quiz round works), and "continue with changes" is an allowed outcome.
* Compliance work could pile up late. -> mitigation: the data protection officer and security team review at G2 and G3, not only at the end.

## Tailoring

| Keep from predictive                                                                                             | Keep from agile                                                                                                       | Drop                                                                                                    |
| ---------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Charter and stakeholder register (the sponsor, data protection officer and security team need a signed baseline) | Two-week sprints with a review (the sponsor sees a working quiz and gives feedback every 2 weeks)                     | Detailed up-front design of every screen (the screens are not specified and will change after feedback) |
| WBS to level 2 and a baselined Must list (needed for the Lab-04 scope baseline)                                  | Prioritised backlog ordered by the product owner (lets the team swap Should and Could items without a change request) | Formal change-request board for backlog items (too heavy for 14 weeks; only Must changes go to a gate)  |
| Four phase gates with measurable evidence (give the approvers fixed decision points)                             | Retrospective after every sprint (the team has no sprint practice and needs to improve quickly)                       | Daily stand-up with a formal log (a short check-in is enough for a small student team)                  |

## Phase gates

| Gate | Week / date      | Evidence required                                                                                                                                                                                               | Decision maker                   | Outcomes                                         |
| ---- | ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------- | ------------------------------------------------ |
| G1   | W3 · 2026-10-19  | 1. Charter signed and the 8 Musts baselined. 2. WBS to level 2, schedule with four sprints and four gates approved. 3. Risk register with owners, including real-time load.                                     | Sponsor (Head of IT) with the PM | continue / continue with changes / stop / repeat |
| G2   | W7 · 2026-11-16  | 1. A full quiz round (join, answer, score) runs live with at least 10 test players. 2. At least 4 of the 8 Musts accepted at sprint reviews. 3. Data protection officer has reviewed the list of personal data. | Sponsor                          | continue / continue with changes / stop / repeat |
| G3   | W11 · 2026-12-14 | 1. All 8 Musts accepted. 2. Load test with 50 simulated players, 95% of answers shown within 2 seconds. 3. No open critical finding from the security team.                                                     | Sponsor with the security team   | continue / continue with changes / stop / repeat |
| G4   | W14 · 2027-01-04 | 1. Pilot with 50 students completed. 2. At least 80% of pilot quiz sessions finished without a crash. 3. Zero open critical defects and a handover note accepted by IT operations.                              | Sponsor with IT operations       | continue / continue with changes / stop / repeat |
