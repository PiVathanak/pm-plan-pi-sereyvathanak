# Project charter: Realtime Quiz platform

| Field   | Value                            |
| ------- | -------------------------------- |
| Version | 1.0 (draft for sponsor approval) |
| Date    | 2026-09-29                       |
| Sponsor | Head of the IT department        |
| PM      | Supervising Lecturer             |

## 1. Purpose and justification

Instructors across the IT department currently spend substantial weekly hours manually grading paper quizzes or administering asynchronous forms that fail to provide immediate classroom learning feedback. The Realtime Quiz project delivers an interactive, self-hosted web platform enabling instructors to author multiple-choice quizzes and facilitate synchronized live quiz sessions with real-time feedback. Participating students join instantly using a 6-character access code, respond against an authoritative timer, and view immediate score updates and leaderboards over WebSocket. This solution eliminates repetitive manual grading, enhances student engagement during lectures, and ensures full departmental ownership and privacy of student assessment data. A comprehensive economic justification comparing this custom build against commercial SaaS alternatives is documented in `business-case.md`.

## 2. Objectives and success criteria

| #  | Objective (what will be true)                                         | Success criterion (number + week)                                                                 |
| -- | --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| O1 | Demonstrate fully functional MVP core covering all Must features      | 100% of Must features verified with 0 critical defects, demonstrated in week 7                    |
| O2 | Conduct a live classroom pilot session with real students             | 50 participants in 1 live session with 0 blocking defects, completed in week 14                   |
| O3 | Maintain real-time broadcast delivery during live quiz sessions       | <= 500 ms latency at the 95th percentile across all clients, verified in week 14                  |
| O4 | Support high concurrent session capacity on standard virtual hardware | 20 concurrent sessions of 100 participants on 2 vCPU and 2 GB RAM, validated in week 13           |
| O5 | Achieve automated quality assurance and CI verification               | >= 80% automated line coverage with 0 broken CI builds on main branch, maintained through week 14 |

## 3. High-level scope

In scope:

- Web-based quiz authoring and management interface for multiple-choice questions
- Live session hosting dashboard with synchronized authoritative question timers
- Real-time student participation interface with instant response submission
- Automated scoring engine and dynamic live session leaderboard
- Role-based authentication system supporting instructor, student, and guest access
- Responsive web user interface supporting desktop and mobile browser form factors
- Quiz session analytics dashboard and export module producing CSV and PDF reports

Out of scope:

- Native mobile applications (no native iOS or Android binaries)
- Non-multiple-choice question formats (no open text, essay, or voice responses)
- Integrated real-time video or audio conferencing capabilities
- Learning Management System (LMS) integration (no LTI or direct Moodle/Canvas gradebook sync)
- Multi-node horizontal scaling infrastructure (single-instance server deployment)

## 4. Milestones

| Week | Milestone                                                         | Ends process group         |
| ---- | ----------------------------------------------------------------- | -------------------------- |
| 1    | Project charter signed, core team onboarded                       | Initiating                 |
| 3    | Architecture baseline and project management plan approved        | Planning                   |
| 5    | Quiz authoring module and live session core integrated            | Executing                  |
| 7    | MVP demo (Must features verified live)                            | Executing                  |
| 10   | Analytics dashboard, result export, and Should features completed | Executing                  |
| 13   | Hardening complete and 100-student load test passed               | Monitoring and controlling |
| 14   | Pilot with 50 students, final documentation, and closure          | Closing                    |

## 5. Budget summary

Effort: students 4 x 14 x 8 h = 448 h; PM 14 x 3 h = 42 h; total 490 h

Cash: hosting 4 x 25 USD = 100 USD; domain 15 USD; tools 60 USD; reserve 25 USD (14 %);

total 200 USD

## 6. Assumptions

- The 4-student development team remains fully committed and contributes an average of 8 hours per week each throughout the 14-week semester without unreplaced attrition.
- Departmental virtual server infrastructure (Linode VPS with 2 vCPU and 2 GB RAM) and domain routing remain continuously available with necessary deployment privileges.
- Campus Wi-Fi and network infrastructure permit outgoing and incoming WebSocket traffic (or allow SockJS fallback over HTTPS) without port blocking.
- The supervising lecturer is available for 3 hours per week to conduct weekly sprint status reviews, evaluate deliverables, and provide architectural direction.

## 7. Constraints

- Fixed timeline: All work must be completed within exactly 14 calendar weeks, starting on 2026-09-29 and concluding with the live pilot and project closure in week 14.
- Hard cash cap: Total direct financial expenditure is strictly capped at 200 USD for the entire duration of the project.
- Hardware limitation: The production system must operate reliably within a single Linode server instance constrained to 2 vCPU and 2 GB RAM.
- Student academic capacity: Individual student effort is constrained to 8 hours per week to comply with capstone course curriculum limits and other academic commitments.

## 8. High-level risks

- Campus proxy blocks WebSocket traffic: Campus network firewalls or transparent HTTP proxies may disrupt persistent WebSocket connections.
  *Mitigation:* Implement SockJS fallback protocol to seamlessly degrade to HTTP long-polling when WebSocket upgrades are rejected.
- Client-server clock drift and answer race conditions: Desynchronized local student clocks may cause valid quiz answers submitted near the deadline to be unfairly rejected.
  *Mitigation:* Enforce an authoritative server-side countdown clock and incorporate a 200 ms latency grace window for in-flight submissions.
- Framework version compatibility hurdles: Spring Boot 4 and Spring Security 7 are bleeding-edge releases with breaking configuration changes and sparse community tutorials.
  *Mitigation:* Build and validate authentication filters and WebSocket security handshakes in initial iterations (weeks 2–3) to mitigate integration risks early.

## 9. Project manager authority

- **Decides alone:** The Project Manager is authorized to re-plan task sequencing, assign work packages among the 4 student developers, approve technical implementation details, and make trade-offs regarding Should/Could scope features within the 490 person-hour allocation and the 25 USD cash contingency reserve.
- **Needs sponsor approval:** The Project Manager requires formal written approval from the Sponsor (within 5 working days of submission) to modify the five core project objectives, alter the Must-feature scope, shift the week-7 MVP demo or week-14 pilot milestones, or incur expenses exceeding the 200 USD total cash ceiling.

## 10. Approval

Sponsor: ____________________  Date: ________
PM:      ____________________  Date: ________
