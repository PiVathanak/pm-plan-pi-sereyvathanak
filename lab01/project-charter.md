# Project charter: Realtime Quiz platform

| Field   | Value                            |
| ------- | -------------------------------- |
| Version | 1.0 (draft for sponsor approval) |
| Date    | 2026-09-29                       |
| Sponsor | Head of the IT department        |
| PM      | Pi sereyVathanak, Tal Tongsreng  |

## 1. Purpose and justification

Lecturers spend significant time marking in-class quizzes by hand and get no live view of how students are doing while a session is running. The Realtime Quiz platform lets a teacher upload a question set, run a live session, and see every student's answers and scores update immediately. This cuts marking effort and lets teachers adjust the lesson on the spot. The costs, benefits and alternatives are analysed in business-case.md (Task 4)

## 2. Objectives and success criteria

| #   | Objective (what will be true)                                         | Success criterion (number + week)                              |
| --- | --------------------------------------------------------------------- | -------------------------------------------------------------- |
| O1  | A working MVP covers question upload, joining, answering, live scores | MVP demo of the full quiz flow with 0 blocking defects, week 7 |
| O2  | Pilot with 50 students in one live session                            | 50 participants, 0 blocking defect, week 14                    |
| O3  | The platform handles more load than the pilot needs                   | 100 concurrent participants in a load test, week 12            |
| O4  | Broadcast latency during the pilot                                    | <= 500 ms at the 95th percentiles, measure in week 14          |
| O5  | Core logic is covered by automated tests                              | >= 70 % line coverage of scoring and session logic, week 13    |

## 3. High-level scope

In scope:

- Question-set import from JSON files with validation
- Teacher session control (create, start, close a quiz session)
- Student join and answer submission
- Real-time score calculation and broadcast
- Live leaderboard for teacher and students
- Teacher results summary after a session
  Out of scope:
- Multi-node horizontal scaling (deferred to next semester)
- Integration with the LMS and grade export
- Native mobile applications
- commercial licensing feature

## 4. Milestones

| Week | Milestone                                        | Ends process group     |
| ---- | ------------------------------------------------ | ---------------------- |
| 1    | Charter approved, team formed                    | Initiating             |
| 3    | backend coding: import question, import, scoring | executing              |
| 7    | MVP demo                                         | Executing              |
| 9    | Complete feature and load testing                | monitoring and control |
| 14   | Pilot with 50 students, closure                  | Closing                |

## 5. Budget summary

Effort: students 4 x 14 x 8 h = 448 h; PM 14 x 3 h = 42 h; total 490 h
Cash: hosting 4 x 25 USD = 100; domain 15; tools 60; reserve 25 (14 %)
total 200 USD

## 6. Assumptions

- The four students are available 8 h per week for all 14 weeks.
- The department provides a test group of 50 students for the week 14 pilot.
- The sponsor or a delegate answers approval requests within 5 working days.
- Pilot participants have devices and campus network access.

## 7. Constraints

- Fixed duration: 14 weeks, pilot in week 14 with no extension.
- Cash cap: 200 USD in total, including the reserve.
- Effort cap: 490 h (448 h student + 42 h PM).

## 8. High-level risks

- Real-time broadcast misses the 500 ms target under load.
- Team members' availability drops during exam periods.
- Scope grows (LMS integration, new features) and threatens the week 7 and week 14 dates.

## 9. Project manager authority

The PM re-plans within the 490 h and 200 USD, assigns tasks, and decides the order of work and technical approach without approval. Adding scope, moving the pilot or milestone dates, changing an objective, or spending beyond the reserve needs the sponsor's written approval within 5 working days.

## 10. Approval

Sponsor: ********\_\_\_\_******** Date: **\_\_\_\_**
PM: ********\_\_\_\_******** Date: **\_\_\_\_**
