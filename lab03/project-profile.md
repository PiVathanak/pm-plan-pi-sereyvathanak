# Project profile · Realtime Quiz

Sources: [charter](../lab01/project-charter.md), [MoSCoW list](../lab02/moscow-list.md)

| #   | Criterion                            | Evidence (one fact)                                                                       | Weight | Score 1-5 | W x S |
| --- | ------------------------------------ | ----------------------------------------------------------------------------------------- | -----: | --------: | ----: |
| 1   | Requirements stability               | 8 Must features fixed in the charter; screens and<br>real-time behaviour not specified    |     40 |         1 |    40 |
| 2   | Technical uncertainty                | Live real-time updates for many players at once are new to the team and untested          |     20 |         5 |   100 |
| 3   | Team experience with agile           | Team 3 is students with no recorded sprint practice; a lecturer acts as PM                |     15 |         3 |    45 |
| 4   | Contract and governance constraints  | Sponsor, data protection officer and security team must approve; VPS run by IT operations |     10 |         4 |    40 |
| 5   | Need for early delivery and feedback | MVP demo in week 7 and a 50-student pilot in week 14                                      |     15 |         5 |    75 |
|     | **Profile** = SUM(W x S) / 100       | (40+100+45+40+75)/100                                                                     |    100 |           |     3 |
| 6   | (optional) Sponsor availability      | Head of IT can plausibly review an increment every two weeks (to confirm)                 |      - |         4 |     - |

Score 1-5: 1 = the fact favours predictive, 5 = it favours adaptive.

Interpretation: < 2.5 predictive · 2.5-3.5 hybrid · > 3.5 agile

## Profile summary

Realtime Quiz is a hybrid project: its scope is fixed on paper (eight Must features) and it needs sign-off from the sponsor, data protection officer and security team, but its real-time technology is new to the team and the week 7 MVP and week 14 pilot demand early feedback. The two dominant criteria are requirements stability (weight 40, score 1, pulling toward predictive) and technical uncertainty (weight 20, score 5, pulling toward adaptive), and they largely cancel out around the middle of the scale. Task 2 must therefore include a hybrid approach among its candidates, alongside a fully predictive option (Waterfall) and a fully agile one (pure Scrum) for comparison.
