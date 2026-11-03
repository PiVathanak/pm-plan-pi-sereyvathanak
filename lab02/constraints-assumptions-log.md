# Constraints and assumptions log · Realtime Quiz · v0.1 · week 6

| Id | Type | Statement (measurable) | Source / owner | Validate by |
|----|------|-------------------------|----------------|-------------|
| C-01 | Constraint | The pilot must run with 50 students in week 14 of the 14-week semester, starting 2026-09-29. | Lab-01 charter, Milestones / Sponsor | fixed |
| C-02 | Constraint | The team has 4 students × 10 h/week = 40 h/week, giving 560 person-hours over 14 weeks; 504 h is planned work and 56 h is contingency. | Lab-02 recap, Resources and Effort capacity / PM | fixed |
| C-03 | Constraint | Direct cash expenditure cannot exceed 200 USD: 100 USD hosting, 15 USD domain, and 85 USD tools and reserve. | Lab-02 recap, Budget / Sponsor | fixed |
| C-04 | Constraint | Production must run on one Linode VPS with 2 vCPU and 2 GB RAM; horizontal multi-node scaling is not available. | Lab-01 charter, Constraints and Out of scope / Technical lead | fixed |
| C-05 | Constraint | The release must keep broadcast latency under 500 ms at the 95th percentile, meet WCAG AA, and maintain at least 80% line coverage with zero broken CI builds on main. | Lab-01 charter, Objectives and DoD / QA lead | fixed |
| A-01 | Assumption | The Linode VPS and domain will remain available for all 14 weeks with deployment privileges for the team. | Lab-01 charter, Assumptions / IT administrator | W2 -> R-01 |
| A-02 | Assumption | Campus Wi-Fi will allow WebSocket traffic, or SockJS over HTTPS will be permitted, during the week-14 pilot. | Lab-01 charter, Assumptions / Network administrator | W3 -> R-02 |
| A-03 | Assumption | Each of the 4 students will contribute 10 h/week through week 14, with no unreplaced absence. | Lab-02 recap, Resources / PM | W2 -> R-03 |
| A-04 | Assumption | The supervising lecturer will provide 2 h/week for review and technical decisions through week 14. | Lab-02 recap, Roles / Lecturer | W2 -> R-04 |
| A-05 | Assumption | The department will confirm 50 pilot students and one classroom session by the end of week 13. | Lab-02 recap, Milestones / Sponsor | W13 -> R-05 |

Review every milestone. An overdue assumption becomes an open issue and its risk id is added to the risk register.
