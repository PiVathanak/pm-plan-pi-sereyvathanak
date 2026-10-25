# Business case: live quizzes for the IT department

## 1. Problem

IT department faculty currently face an unsustainable administrative workload when preparing, administering, and manually marking weekly classroom quizzes. Instructors spend valuable teaching preparation time grading papers or collating spreadsheet forms, while students receive feedback days or weeks after lectures when the pedagogical moment has passed. Furthermore, existing paper assessments fail to provide real-time engagement or immediate diagnostic insights into student comprehension during lectures.

Assumptions:
- Lecturers running weekly quizzes: 10
- Marking time per lecturer per week: 1 h
- Teaching weeks per academic year: 30
- Notional value of one faculty/student hour: 10 USD (used to value labor and compare options on an equitable economic baseline)
- Total annual faculty grading effort: 10 lecturers x 1 h/week x 30 weeks = 300 hours/year
- Annual cost of grading time: 300 hours x 10 USD/h = 3,000 USD/year

## 2. Options

| Option | Description | One-off cost | Annual cost | Annual benefit |
|--------|-------------|--------------|-------------|----------------|
| A | Do nothing | 0 USD | 0 USD | 0 USD |
| B | Buy Quiz SaaS (e.g., Kahoot! 360 EDU / AhaSlides) | 0 USD | 1,800 USD | 3,000 USD |
| C | Build Realtime Quiz in-house (capstone project) | 4,900 USD | 300 USD | 4,800 USD |

*Note on Option B pricing:* Based on educational SaaS market pricing (Kahoot! Higher Education Pro plan baseline cited at ~15 USD per host/lecturer per month as of October 2026; assumed at 10 lecturers x 15 USD x 12 months = 1,800 USD/year).

*Note on Option C costs:* One-off development effort includes 448 hours student effort + 42 hours supervising lecturer guidance = 490 person-hours valued notionally at 10 USD/h (4,900 USD); direct out-of-pocket cash is capped at 200 USD. Annual cost represents Linode VPS hosting at 25 USD/month x 12 months = 300 USD/year. Annual benefit combines 3,000 USD in saved marking labor plus 1,800 USD in avoided commercial SaaS license fees.

## 3. Comparison

| Option | Net annual benefit | Payback (years) | Sensitivity (6 lecturers) |
|--------|--------------------|-----------------|----------------------------|
| B | 3,000 - 1,800 = 1,200 USD | 0 (no one-off cost) | 1,800 - 1,080 = 720 USD (Payback: 0 years) |
| C | 3,000 + 1,800 - 300 = 4,500 USD | 4,900 / 4,500 = 1.09 (~1.1 years) | Net benefit 2,880 USD: 4,900 / 2,880 = 1.70 years (or 2,580 USD net of hosting: 1.90 years) |

*Calculations reference:* Detailed formula-level calculations are provided in [business-case.csv](file:///c:/Users/USer/Documents/techno/ITSM_ITSoftwareMananagement/pm-plan-CheaSeavhong/lab01/business-case.csv).

## 4. Benefits not priced

- **Capstone Educational Outcomes:** Delivers practical, high-impact software engineering and DevOps experience for 4 undergraduate students working with modern enterprise technologies (Spring Boot, WebSocket STOMP, PostgreSQL, Docker Compose, CI/CD).
- **Institutional Data Sovereignty and Privacy:** Student identities, answer histories, and assessment performance are stored exclusively on campus-controlled infrastructure, avoiding external FERPA/GDPR third-party cloud data compliance liabilities.
- **No Per-Seat or Participant Throttling:** Commercial platforms restrict participant caps and feature sets behind higher pricing tiers; the in-house platform supports unlimited concurrent students and sessions within hardware limits without recurring license escalation.
- **Localized Academic Customization:** Enables direct customization for university requirements, such as native Khmer font typography rendering in PDF/CSV reports and seamless compatibility with departmental identity workflows.

## 5. Risks per option

### Option A: Do nothing
- **Faculty Fatigue and Disengagement:** Continued manual marking burden degrades instructor morale and disincentivizes frequent formative quizzes.
- **Delayed Learning Interventions:** Students remain unaware of conceptual mistakes until formal exams, increasing course failure and dropout rates.

### Option B: Buy SaaS
- **Subscription Price Escalation and Lock-in:** Educational SaaS vendors frequently restructure subscription tiers, creating perpetual budget vulnerabilities.
- **Data Compliance and Hosting Restrictions:** Third-party storage of student grades and identification data introduces regulatory and privacy hurdles that may conflict with university policy.
- **Participant Concurrency Restrictions:** Class sizes exceeding license seat tiers incur unexpected penalty costs or lock out enrolled students during live lectures.

### Option C: Build Realtime Quiz
- **Campus Proxy WebSocket Blocking:** Network firewalls or campus web proxies may reject raw WebSocket connections during classroom sessions (*Mitigation: implement SockJS fallback protocol to gracefully downgrade to HTTP long-polling*).
- **Client Clock Drift and Race Conditions:** Asynchronous device clocks may cause valid student answers to arrive after question closing (*Mitigation: enforce authoritative server countdown with a 200 ms network latency grace window*).
- **Framework Evolution and Bleeding-Edge APIs:** Newer releases of Spring Boot 4 and Spring Security 7 have limited tutorial coverage (*Mitigation: construct and validate core security filters and STOMP channels during weeks 2–3*).
- **MVP Scope Creep:** Team may prioritize optional features (chat, question banks) over essential Must-have core deliverables (*Mitigation: strictly enforce milestone gates and PM scope authority*).

## 6. Recommendation and review gate

### Recommendation
Proceed with **Option C (Build Realtime Quiz)**. Option C breaks even and achieves complete notional payback within **1.09 academic years** (~1.1 years) under baseline assumptions (10 lecturers), and within **1.70 to 1.90 years** under a conservative sensitivity scenario (6 lecturers). Beyond economic viability, Option C preserves student data ownership on departmental servers, eliminates perpetual per-seat vendor fees, and fulfills vital capstone learning objectives for the IT department.

### Review Gate
Project continuation is tied to a strict phase gate at **Week 7 (MVP Demo)**:
- If the student team successfully demonstrates all Must features (quiz authoring, live session core, authoritative timer, instant scoring, and live leaderboard with 0 critical defects) at the week-7 milestone review, Option C proceeds to phase 2 (hardening and pilot).
- If the week-7 MVP demo fails to meet core acceptance criteria, the Sponsor will terminate custom development, reallocate remaining resources, and switch to **Option B (Buy SaaS)** for the subsequent semester.

This recommendation directly underpins the project justification established in Section 1 of [project-charter.md](file:///c:/Users/USer/Documents/techno/ITSM_ITSoftwareMananagement/pm-plan-CheaSeavhong/lab01/project-charter.md).
