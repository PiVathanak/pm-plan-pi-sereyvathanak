# Business case: live quizzes for the IT department

## 1. Problem

Lecturers mark in-class quizzes by hand and get no live view of how students are doing.
Assumptions:

- lecturers running quizzes: 10
- marking time per lecturer per week: 1 h
- teaching weeks per year: 30
- notional value of one hour: 10 USD (students are unpaid; used to compare)
- marking effort per year: 10 x 1 x 30 = 300 h, worth 300 x 10 = 3,000 USD
- SaaS price (option B): 15 USD per lecturer per month, an assumption (no pricing page researched)
- hosting for C after the build: 25 USD per month

## 2. Options

| Option | Description                                                    | One-off cost | Annual cost           | Annual benefit                                 |
| ------ | -------------------------------------------------------------- | ------------ | --------------------- | ---------------------------------------------- |
| A      | Do nothing                                                     | 0            | 0                     | 0                                              |
| B      | Buy SaaS: 10 x 15 x 12 = 1,800 USD per year                    | 0            | 1,800                 | 3,000                                          |
| C      | Build Realtime Quiz: 490 h x 10 = 4,900 + 200 USD cash = 5,100 | 5,100        | 300 (hosting 12 x 25) | 3,000 marking + 1,800 SaaS fee avoided = 4,800 |

Full lines and formulas are in business-case.csv.

## 3. Comparison

| Option | Net annual benefit          | Payback (years)      | Sensitivity (6 lecturers)                                 |
| ------ | --------------------------- | -------------------- | --------------------------------------------------------- |
| B      | 3,000 - 1,800 = 1,200       | 0 (no one-off cost)  | 1,800 - 1,080 = 720                                       |
| C      | 3,000 + 1,800 - 300 = 4,500 | 5,100 / 4,500 = 1.13 | 1,800 + 1,080 - 300 = 2,580; payback 5,100 / 2,580 = 1.98 |

Note: C's benefit counts the SaaS fee it avoids, which is a comparison with B. Against doing nothing, C's net is 3,000 - 300 = 2,700 USD and payback is 5,100 / 2,700 = 1.89 years. The recommendation holds either way.

## 4. Benefits not priced

- Learning outcome: the team builds and operates a real-time system as a capstone project.
- Data ownership: student names and results stay on department servers under the data protection officer's retention rule.
- No per-seat limit: more lecturers or students cost nothing extra, while SaaS cost grows with every seat.
- A reusable platform the department can extend (for example the multi-node scaling planned for next semester).

## 5. Risks per option

**A: Do nothing**

- Marking load stays at about 300 h per year.
- Lecturers get no live feedback, so the problem persists and may push them to ad-hoc tools with no data control.

**B: Buy SaaS**

- Student data is stored by a third party, which the data protection officer may not approve.
- Cost grows with every added lecturer, and the vendor can change prices or terms.
- The tool may not accept the department's JSON question format, and there is no learning outcome.

**C: Build**

- Broadcast latency misses the 500 ms target under load.
- Team availability drops during exam periods.
- Scope grows and threatens the week 7 and week 14 dates.
- Running costs fall on the department after handover (hosting, patches, support).

## 6. Recommendation and review gate

Choose option C. Net annual benefit is 4,500 USD and payback is about 1.1 years, still about 2.0 years with only 6 lecturers. The department keeps its data and gets the capstone learning outcome.

Review gate: if the week 7 MVP demo fails, buy option B for the next semester and treat the build as a two-semester project.
