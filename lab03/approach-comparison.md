# Approach comparison · Realtime Quiz

| Approach   | Requirements                                                                                                      | Sponsor control                                                                                                        | First quiz | Two main risks                                                                                                                                                                                            | Fit                                                                                                             |
| ---------- | ----------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Waterfall  | Frozen in the charter and a full specification before any build; changes need a formal change request             | Phase gates (requirements, design, build, test) with sign-off at each; the sponsor sees the product only at acceptance |    week 12 | 1. Real-time problems appear only at integration, too late to fix. 2. Unspecified screens are built wrong and reworked after a late demo.                                                                 | Weak: matches the fixed Must list and approvals, but ignores the technical uncertainty and the week 7 MVP demo. |
| Pure Scrum | Product backlog ordered by the product owner; the 8 Musts are the first items and details emerge per sprint       | Sprint reviews and backlog ordering; no formal approval gates                                                          |     week 2 | 1. The data protection officer and security team get no fixed approval points, so compliance blockers surface late. 2. A team new to Scrum may run ceremonies badly and let scope drift past the 8 Musts. | Partial: strong on uncertainty and early feedback, weak on team experience and governance.                      |
| Hybrid     | Musts and release goals fixed at gate 1; screens and real-time details refined sprint by sprint within that scope | Gates at plan, MVP (week 7) and pilot readiness (week 14), with sprint reviews between them                            |     week 4 | 1. Gates turn into paperwork and slow the sprints. 2. Gate criteria fixed too early lock in decisions before the team has learned enough.                                                                 | Strong: matches the 2.55 hybrid profile (fixed scope on paper, uncertain technology, early milestones).         |

Columns:

· how requirements are handled

· how the sponsor controls the project  
(governance)

· week in which the sponsor first plays a working quiz · two main  
risks

· fit with the Task 1 profile

## Weighted score (from approach-scoring.csv)

Waterfall 2.4 · Scrum 3.3· Hybrid 3.4

## Sensitivity

I find "Team experience with agile" the hardest to judge, because the charter does not record the team's sprint practice, so tests 1 and 2 change its weight. Test 3 changes technical uncertainty, because the gap between Hybrid and Scrum is only 0.10.

- Test 1: Moving +10 to team experience (25) and -10 from requirements stability (30) gives Waterfall 2.50, Scrum 3.50 and Hybrid 4.00, so the ranking does not change.
- Test 2: Moving +10 to team experience (25) and -10 from early delivery (5) gives Waterfall 2.80, Scrum 3.20 and Hybrid 4.00, so the ranking does not change.

## Recommendation

Choose the Hybrid approach (4.00), with Pure Scrum as the runner-up (3.40). Hybrid keeps fixed gates for the sponsor, data protection officer and security team, while sprints reduce the real-time technical risk and give a working quiz by week 4. I would choose Scrum instead if the sponsor, data protection officer and security team agreed to approve at sprint reviews rather than at gates, because the governance advantage of Hybrid would then disappear.
