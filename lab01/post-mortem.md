# Post-mortem: TODO case name (TODO year)

## 1. Timeline and sources

| #   | When                   | Event                                                                                                               | Source                     |
| --- | ---------------------- | ------------------------------------------------------------------------------------------------------------------- | -------------------------- |
| 1   | Start of semester      | A university asks its IT unit for one app covering canteen payments and library fines, to be built in one semester. | fictional case from Lab-01 |
| 2   | Start of semester      | The head of finance "sponsors" the project by e-mail but never attends a review.                                    | fictional case from Lab-01 |
| 3   | Start of semester      | The lead developer is also the PM; success is defined only as "launch in September".                                | fictional case from Lab-01 |
| 4   | During build           | A survey leads to new requirements (bus tickets, parking) with no re-planning.                                      | fictional case from Lab-01 |
| 5   | Before launch          | No test with real card terminals is run.                                                                            | fictional case from Lab-01 |
| 6   | Launch day (September) | Terminals reject 40 % of payments and the canteen queue doubles.                                                    | fictional case from Lab-01 |
| 7   | Day 3 after launch     | The app is withdrawn.                                                                                               | fictional case from Lab-01 |
| 8   | About 5 months later   | Relaunch for the canteen only.                                                                                      | fictional case from Lab-01 |

## 2. Classification and organisation

Project / programme: One project but sound like 3, Canteen payment, Bus ticket and parking after survey.

Structure and PM authority: Team Lead act as a PM and coder at the same time.  
Sponsor, charter, PMO: head of finance was the sponsor but never attend review

## 3. Success criteria

Stated: build a cashless payment app for the canteen and the library fines in one semester and lauch in september

Missing measurable criteria: payment success rate, canteen queue time, number of concurrend that handle user, budget and limit,  
Ignored dimensions (benefits, users, operations, team): benefits (no business case for the queue or the finance office), users (students and canteen staff were not part of any test, and the survey was not turned into a decision), operations (no plan for support, terminal failures or rollback after launch) and team (one person carried management and development).

## 4. Process groups and knowledge areas

| Process group              | What went wrong or was skipped                                                                                                                                                          |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Initiating                 | No charter; the head of finance never accepted the sponsor role, so nobody could refuse the bus-ticket scope.                                                                           |
| Planning                   | Planning stopped at a date; no scope baseline, test plan or risk plan, and the survey requirements were added without re-planning.                                                      |
| Executing                  | The PM was also the main coder, so the build absorbed the management time; features grew while integration with the card terminals was not started.                                     |
| Monitoring and controlling | Progress was reported as "on schedule" without a single end-to-end test, the invisibility trap; there was no change control and no gate before launch.                                  |
| Closing                    | The app was withdrawn after three days with no pilot, no acceptance and no recorded lessons learned; the relaunch scope (canteen only) shows what should have been agreed at the start. |

Knowledge areas most responsible:

1. **Scope management.** Requirements grew from canteen payments to bus tickets and parking after a survey (event 4) with no change control.
2. **Quality management.** No test with real card terminals (event 5) led directly to the 40 % rejection rate on launch day (event 6).
3. **Stakeholder management.** The sponsor never attended a review (event 2), so nobody with authority challenged the date, the scope or the lack of testing.

## 5. Ethics

Decision examined: the PM and the sponsor allowed the app to go live on a fixed date without testing on real terminals, and the status was reported as "on schedule".

- **Responsibility:** the team owned the outcome for students and canteen staff and still launched an untested payment system, so it accepted the risk on their behalf.
- **Respect:** real people paid for lunch with a system that failed 40 % of the time and doubled the queue; the users were treated as the test.
- **Fairness:** the cost of the failure fell on students and staff, while the people who set the date carried none of it.
- **Honesty:** reporting "on schedule" with no end-to-end evidence gave the sponsor and users a false picture of readiness. This is the weakest point of the case.

## 6. What our project will do differently

| #   | Commitment (We will ...)                                                                                                                        | Measured by                                                                                               | By week | Charter line                                |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- | ------- | ------------------------------------------- |
| 1   | We will hold a signed charter with a named sponsor who attends the week 7 and week 13 gates                                                     | signature on the charter, gate minutes                                                                    | 1       | section 10 approval, authority clause       |
| 2   | We will run a load test with 100 simulated students on the real campus Wi-Fi before the pilot                                                   | load test report, 0 blocking errors, latency <= 500 ms at the 95th percentile                             | 12      | O3 latency, milestone week 12               |
| 3   | We will hold the scope to the in-scope list and send every new feature (for example LMS integration) to the sponsor as a written change request | change log with sponsor decision on each request within 5 working days                                    | 14      | section 3 out of scope, section 9 authority |
| 4   | We will demonstrate the working quiz flow end to end, not report percent complete                                                               | MVP demo with 0 blocking defects, with status reports that link to test results                           | 7       | O1, milestone week 7                        |
| 5   | We will run a pilot with defined acceptance and write lessons learned, with a fallback if the pilot readiness gate fails                        | pilot with 50 participants and 0 blocking defects, lessons-learned document, go/no-go decision at week 13 | 14      | O2, milestone week 14, constraint: 14 weeks |
