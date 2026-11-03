# Task 3: Weighted Scoring Matrix

## 1. Purpose

This matrix compares three options for the Realtime Quiz project: Build, Buy SaaS, and Hybrid. The purpose is to select the option that provides the best balance between learning value, cost, time, and requirements fit.

## 2. Options

| Option | Description |
|---|---|
| Build | The four-student team develops the Realtime Quiz system from scratch. |
| Buy SaaS | Use Kahoot!+ Bronze, an existing hosted quiz platform. It supports up to 50 participants and costs $9 per month with monthly billing. |
| Hybrid | Develop the important Realtime Quiz functions while using an existing hosted service for selected supporting functions. |

Kahoot! pricing and participant information were checked on 2026-11-03 using its official pricing page.

## 3. Criteria and weights

The team agreed on these weights on 2026-10-06, before scoring the options.

| Criterion | Weight | Reason |
|---|---:|---|
| Learning value | 40 | The project should provide practical software development experience. |
| Cost | 25 | The project must stay within the $200 cash budget. |
| Time | 20 | The team must finish before the Week 14 pilot. |
| Requirements fit | 15 | The solution must support the Realtime Quiz requirements. |
| **Total** | **100** | |

## 4. Scoring scale

- 1 = Very poor
- 2 = Poor
- 3 = Average
- 4 = Good
- 5 = Excellent

## 5. Scoring results

| Criterion | Weight | Build | Buy SaaS | Hybrid |
|---|---:|---:|---:|---:|
| Learning value | 40 | 5 | 1 | 3 |
| Cost | 25 | 4 | 3 | 3 |
| Time | 20 | 3 | 5 | 4 |
| Requirements fit | 15 | 5 | 3 | 4 |
| **Weighted score** | **100** | **435** | **260** | **335** |
| **Percentage of maximum** | | **87%** | **52%** | **67%** |

## 6. Evidence for scores

### Learning value
- Build (5): The team develops the application and practices frontend, backend, database, and real-time communication.
- Buy SaaS (1): Most development and technical work are handled by the service provider.
- Hybrid (3): The team develops selected features but relies on an existing service for other functions.

### Cost
- Build (4): The team uses its $200 budget for hosting, domain, and tools. Development is completed by students.
- Buy SaaS (3): Kahoot!+ Bronze costs $9 per month with monthly billing. Four months would cost $36 before any applicable changes or fees.
- Hybrid (3): The team pays for hosting and may also need a subscription for the external service.

### Time
- Build (3): The team must design, develop, test, and fix the application within the semester.
- Buy SaaS (5): The hosted platform is already available and can be used quickly.
- Hybrid (4): Existing services reduce some development work, but integration is still required.

### Requirements fit
- Build (5): The team can design the system around the project's specific requirements.
- Buy SaaS (3): The existing platform supports live quizzes but may not support all custom requirements.
- Hybrid (4): Custom features can be developed while existing services provide selected functions.

## 7. Sensitivity analysis

To test whether the result changes when priorities change, 10 points are moved from the heaviest criterion (Learning value) to the lightest criterion (Requirements fit).

| Criterion | Original weight | New weight |
|---|---:|---:|
| Learning value | 40 | 30 |
| Cost | 25 | 25 |
| Time | 20 | 20 |
| Requirements fit | 15 | 25 |
| **Total** | **100** | **100** |

Recalculated scores:

- Build = (30 × 5) + (25 × 4) + (20 × 3) + (25 × 5) = **425**
- Buy SaaS = (30 × 1) + (25 × 3) + (20 × 5) + (25 × 3) = **280**
- Hybrid = (30 × 3) + (25 × 3) + (20 × 4) + (25 × 4) = **340**

Build remains the winner after changing the weights. Therefore, the decision is not sensitive to this 10-point change.

## 8. Recommendation

The team recommends **Build** because it has the highest weighted score of 435 (87%). It provides the strongest learning value and the best fit for the project's specific requirements. Although Buy SaaS is faster, it provides less development experience and may not support all custom requirements. Hybrid is a reasonable alternative, but its score is still lower than Build.

## 9. Sources

- Kahoot! official school plans and pricing: https://kahoot.com/schools/plans/
- Kahoot! participant limits: https://support.kahoot.com/hc/en-us/articles/115003072287-How-many-participants-can-play-a-kahoot
- Scoring calculations: `lab02/scoring.csv`