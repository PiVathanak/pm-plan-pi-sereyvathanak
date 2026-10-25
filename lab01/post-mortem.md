# Post-Mortem: CampusPay Wallet (2026)

## 1. Timeline and Sources

| # | When | Event | Source |
|---|------|-------|--------|
| 1 | Month 1 (Feb) | University administration requests IT unit to build a cashless payment app for the campus canteen and library fines within one semester; Head of Finance sends email agreement. | Fictional case from Lab-01 brief |
| 2 | Month 2 (Mar) | The lead developer is appointed dual roles as project manager and sole programmer, without a signed charter, clear governance, or an assigned steering committee. | Fictional case from Lab-01 brief |
| 3 | Month 3 (Apr) | Following an informal student survey, requirements expand to incorporate campus bus tickets and parking fee payments without adjusting schedule or resource allocations. | Fictional case from Lab-01 brief |
| 4 | Month 4 (Jun–Jul) | Development proceeds focusing solely on UI coding; status is reported as "on schedule" without any integration testing against physical canteen card terminals. | Fictional case from Lab-01 brief |
| 5 | Month 5 (Late Aug) | The application is pushed directly to production to satisfy the nominal target of "launch in September" without rehearsal, cashier training, or readiness sign-off. | Fictional case from Lab-01 brief |
| 6 | Launch Day (1 Sep) | Physical point-of-sale card terminals reject 40% of transactions; queues in the canteen double; manual cash workarounds collapse lunch operations. | Fictional case from Lab-01 brief |
| 7 | Day 3 Post-Launch (4 Sep) | Under intense student and staff backlash, university executive leadership formally withdraws the CampusPay application from service. | Fictional case from Lab-01 brief |
| 8 | Month 10 (Feb +1) | The application relaunches five months later with a drastically stripped-down scope restricted solely to canteen payments under proper supervision. | Fictional case from Lab-01 brief |

## 2. Classification and Organisation

- **Project / Programme:** The initiative was conceived as a temporary project intended to deliver a unique product (canteen and library cashless payments) in one semester. However, when disparate requirements (bus tickets and parking) were added without structural coordination, it mutated into an unmanaged, uncoordinated programme of distinct payment domains that lacked individual project charters or a unified programme benefits framework.
- **Structure and PM Authority:** The project existed within a weak functional matrix. The PM was a technical lead with zero formal project authority to push back on scope additions, negotiate dedicated testing hardware, enforce freeze gates, or escalate unmanaged dependencies to executive leadership.
- **Sponsor, Charter, PMO:**
  - *Sponsor:* The Head of Finance acted as an absent "sponsor in name only" who confirmed the initiative by email but never attended sprint reviews, milestone gates, or budget reviews.
  - *Charter:* No formal project charter was ever written, baselined, or signed, leaving objectives and authority undefined.
  - *PMO:* There was no Project Management Office (PMO) or departmental oversight to enforce quality checks, risk logs, or operational handover standards.

## 3. Success Criteria

- **Stated Criteria:** A single, vague calendar milestone: "launch in September".
- **Missing Measurable Criteria:**
  - *Transaction Success Rate:* Terminal transaction acceptance rate >= 99.5% under peak lunch traffic (zero unhandled rejected payments).
  - *Latency / Performance:* End-to-end checkout processing latency <= 2 seconds per card swipe.
  - *Concurrency Capacity:* Sustained throughput of 200 concurrent transactions/minute across 10 campus terminals without database lockup.
  - *Operational Efficiency:* Canteen checkout queue time reduced by >= 25% compared to cash handling.
- **Ignored Dimensions:**
  - *Business Benefits:* Reduction in cash-handling costs and automated general ledger reconciliation were never measured.
  - *User Satisfaction:* Student transaction confidence and canteen cashier usability were neglected; offline network recovery was absent.
  - *Operational Readiness:* Canteen staff training, error recovery runbooks, POS terminal driver validation, and helpdesk support procedures were completely skipped.
  - *Team Health:* A single developer shouldered PM, coding, testing, and deployment duties without realistic capacity buffers, leading to severe burnout.

## 4. Process Groups and Knowledge Areas

| Process group | What went wrong or was skipped |
|---------------|--------------------------------|
| Initiating | Skipped the project charter and governance setup; the sponsor was nominal and absent, leaving project objectives and boundaries ungrounded. |
| Planning | Failed to create a WBS, quality management plan, or risk management strategy, omitting physical hardware integration testing entirely. |
| Executing | The developer wrote features in isolation with no iterative user releases, focusing on UI screens rather than payment gateway reliability. |
| Monitoring and controlling | Suffered from the "invisibility trap," reporting status as "on schedule" based on lines of code rather than working, verified integration tests. |
| Closing | Skipped pre-flight pilot testing and operational handover, converting launch day into an unmanaged live test that caused catastrophic failure. |

**Three Knowledge Areas Most Responsible:**
1. **Project Scope Management:** Requirements exploded uncontrollably from canteen/library payments to bus tickets and parking based on an informal survey, without formal change request evaluation, WBS adjustment, or sponsor approval.
2. **Project Quality Management:** Zero quality assurance gates were enforced; no unit test coverage benchmarks or physical terminal integration tests were conducted prior to launch day, directly causing the 40% terminal rejection failure.
3. **Project Stakeholder & Governance Management:** The executive sponsor never attended reviews, target cashiers were never consulted, and the PM lacked governance channels to escalate terminal hardware defects.

## 5. Ethics

- **Decision Examined:** The project leadership's decision to deploy the CampusPay platform to live production on 1 September, knowing that no end-to-end integration test with real physical POS terminals had ever been conducted.
- **Evaluation against PMI Code of Ethics & Professional Conduct:**
  - *Responsibility:* **Violated.** Leadership abandoned its professional responsibility to deliver a safe, operational tool, passing known technical debt and catastrophic operational disruption onto students and canteen workers.
  - *Respect:* **Violated.** Disregarded the livelihood and daily workflow of canteen cashiers, who endured furious customer queues, and students whose scheduled lunch hours were disrupted.
  - *Fairness:* **Violated.** Unfairly subjected students to financial vulnerability (unreliable transactions and payment uncertainty) without transparent dispute resolution or cash fallback workflows.
  - *Honesty:* **Violated.** Deceived the university community by announcing the service was ready for "launch in September," masking unverified core payment mechanisms behind superficial UI completion.

## 6. What Our Project Will Do Differently

| # | Commitment (We will ...) | Measured by | By week | Charter line |
|---|--------------------------|-------------|---------|--------------|
| 1 | We will execute a full simulated live session with 100 concurrent virtual participants and real campus network Wi-Fi before exposing the system to students | Automated load test report showing 0 server crashes and 95th percentile latency <= 500 ms | Week 13 | Objective O3 (latency), Objective O4 (capacity), Milestone Week 13 |
| 2 | We will hold a formally signed project charter with an active Sponsor who attends and signs off on the Week 7 MVP and Week 13 pilot readiness review gates | Formal sponsor signatures on charter and phase gate evaluation records | Weeks 1, 7, and 13 | Milestone Week 1, Section 9 (Authority), Section 10 (Approval) |
| 3 | We will strictly enforce scope boundaries around core Must features and freeze all optional Could features (chat, question banks) until after the MVP demo | 100% of Must features verified with zero unapproved scope items merged into the main release branch | Week 7 | Objective O1 (Must features), Section 3 (Out of Scope exclusions) |
| 4 | We will implement authoritative server-side countdown timers with an automatic 200 ms latency window and SockJS HTTP long-polling fallback to guarantee zero rejected submissions | Zero rejected valid answers and 100% successful proxy fallback rate verified in simulated network latency tests | Week 10 | Section 8 High-Level Risks (WebSocket proxy blocking and clock drift) |
| 5 | We will produce a complete operational runbook, Docker Compose production deployment configuration, and data privacy clearance from the DPO prior to live deployment | Signed operational acceptance by IT Operations (S06) and formal student data clearance by Data Protection Officer (S08) | Week 13 | Stakeholders S06 & S08 expectations, Milestone Week 13 (Pilot readiness) |
