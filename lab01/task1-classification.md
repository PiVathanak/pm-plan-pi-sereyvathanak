# Task 1: project, operation or programme?

| # | Initiative | Temporary? | Unique? | Coordinated? | Class | Justification |
|---|------------|------------|---------|--------------|-------|---------------|
| 1 | Build the Realtime Quiz platform and pilot it with 50 students in week 14 | yes | yes | no | Project | It has a definite end date in week 14 and delivers a completely new platform that did not exist before. |
| 2 | Run the nightly backup of the gicitc.com PostgreSQL database | no | no | no | Operation | Repeats every night with the same output and no end date; it is part of keeping the service running. |
| 3 | Move the department's three web servers to a new Linode region before 15 December | yes | yes | no | Project | It has a fixed deadline of 15 December and completes a one-off migration that finishes when the last server is moved. |
| 4 | Answer helpdesk tickets within the 4-hour service level | no | no | no | Operation | It is a continuous operational service measured by an ongoing service level rather than a defined finish date. |
| 5 | "Digital classroom": Realtime Quiz, LMS upgrade and lecture capture sharing one login and one grade export | yes | yes | yes | Programme | Three related projects; the shared login and grade export are a benefit that none of them delivers alone, so they are coordinated. |
| 6 | Apply the monthly security patches to the VPS | no | no | no | Operation | It is a routine, recurring maintenance schedule with no end date, aimed at sustaining system security. |
| 7 | Add multi-node scaling (RabbitMQ relay, Redis registry) to Realtime Quiz next semester | yes | yes | no | Project | It has a clear timeframe of next semester and creates a new architectural capability that did not previously exist. |
| 8 | Operate the Realtime Quiz platform after go-live: password resets, restarts, monitoring | no | no | no | Operation | It consists of ongoing, repetitive support activities required to keep the service operational after go-live. |
| 9 | Write and publish the department's annual IT report for the dean by 31 January | yes | yes | no | Project | It has a strict deadline of 31 January and produces a unique report detailing that specific year's performance. |
| 10 | Replace 40 wireless access points in two buildings during the summer break | yes | yes | no | Project | It has a finite window (the summer break) and delivers a one-time physical network replacement. |

## Grey zones

- **Initiative 7 (Add multi-node scaling to Realtime Quiz next semester):** This could be classified as an operation if viewed as an incremental software maintenance release, or as a project if it introduces significant new architecture. It would be settled by knowing who authorised the work, whether a separate budget and charter were allocated, and how "done" is formally defined.
- **Initiative 9 (Write and publish the department's annual IT report for the dean by 31 January):** This could be argued as an operation because it repeats cyclically every year, or as a small project because each report requires fresh data, unique analysis, and meets a hard deadline. It would be settled by checking whether staff are assigned through normal operational duties or if a temporary project team and budget are explicitly established.

## What our project hands over

At go-live in week 14, the Realtime Quiz project team hands over the platform to the department's IT operations and helpdesk team for ongoing monitoring and user support. The operations team takes responsibility for routine administration, including password resets, server restarts, scheduled backups, and triaging incident tickets. To operate the service smoothly, the team needs deployment documentation, standard operating procedure runbooks, admin credentials, monitoring alert dashboards, and an escalation path back to developers for critical bugs.
