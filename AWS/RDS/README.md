# AWS Aurora Project Assignments — Senior DBA Training

Ten progressive projects built around one application. The early projects establish AWS competence; the later projects assess operating Aurora under pressure, including troubleshooting, migration, recovery, and architecture judgment.

## Common Business Scenario

You are the DBA for an online retailer. Its order database must support transactional writes, reporting queries, seasonal traffic spikes, and business continuity.

Use **Aurora PostgreSQL** throughout, or run a separate Aurora MySQL track. Document the chosen engine version, AWS Region, and feature compatibility. Adapt PostgreSQL-specific steps for the MySQL track.

Use synthetic tables such as `customers`, `products`, `orders`, `order_items`, and `payments`. Start with approximately 100,000 orders and increase the dataset when performance testing requires it.

## Requirements for Every Assignment

- Use a dedicated training environment and synthetic data.
- Keep databases private, restrict network access, encrypt storage, and validate TLS connections.
- Store credentials securely; application users must not use the master account.
- Record infrastructure changes in Terraform or CloudFormation, with scripts for operations the chosen tool does not support.
- Tag resources by candidate and project. Submit a cost estimate, budget alerts, and cleanup instructions. Budget alerts are notifications, not a spending cap.
- Submit runnable evidence: configuration, SQL, workload scripts, timestamped results, and runbooks. Screenshots alone are insufficient.

These security requirements align with [AWS Aurora security guidance](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/CHAP_BestPractices.Security.html).

## Projects: Lower to Higher Difficulty

| Project | Difficulty | Suggested Effort |
|---|---|---|
| 1. [Build a production-style Aurora foundation](./01-aurora-foundation.md) | Foundation | 4–6 hours |
| 2. [Recover from accidental data deletion](./02-accidental-deletion-recovery.md) | Foundation+ | 6–8 hours |
| 3. [Prove high availability from the application’s perspective](./03-high-availability-and-failover.md) | Intermediate | 8–10 hours |
| 4. [Diagnose and tune a slow order-processing workload](./04-performance-diagnostics-and-tuning.md) | Intermediate | 10–12 hours |
| 5. [Implement and test database access controls](./05-database-access-controls.md) | Intermediate+ | 8–10 hours |
| 6. [Survive a connection storm with RDS Proxy](./06-rds-proxy-and-connection-storms.md) | Advanced | 8–10 hours |
| 7. [Choose an Aurora capacity and cost strategy](./07-capacity-and-cost-strategy.md) | Advanced | 10–12 hours |
| 8. [Migrate a live PostgreSQL database into Aurora](./08-live-migration-with-dms.md) | Advanced+ | 12–16 hours |
| 9. [Upgrade Aurora with a controlled Blue/Green deployment](./09-blue-green-engine-upgrade.md) | Expert | 10–14 hours |
| 10. [Design and operate cross-Region disaster recovery](./10-global-database-disaster-recovery.md) | Senior DBA capstone | 16–20 hours |

Reuse the business workload and suitable infrastructure between projects. Use separate lab clusters when a feature combination requires it, and remove temporary resources after collecting evidence.

## Submission Package

Each candidate submits:

1. A repository containing infrastructure definitions, SQL, and workload scripts.
2. A one-page architecture and decision summary.
3. A runbook another candidate can execute.
4. An evidence table: test, expected result, actual result, timestamp, and supporting log or metric.
5. Cost assumptions, resource inventory, and cleanup confirmation.
6. A 15-minute demonstration followed by troubleshooting questions.

## Scoring Rubric

Apply this rubric to each project.

| Area | Points | What Earns a Strong Score |
|---|---:|---|
| Correctness and data integrity | 25 | Correct results, reconciliation, safe retries |
| AWS implementation and security | 25 | Appropriate networking, IAM, credentials, encryption |
| Operational judgment | 20 | Clear recovery procedures, abort criteria, realistic tradeoffs |
| Evidence and reproducibility | 20 | Repeatable tests and measurements supporting claims |
| Cost and communication | 10 | Complete estimates and clear handover |
| **Total** | **100** | |

Suggested pass mark: **75/100**, with remediation required for exposed credentials, unjustified public database access, or unexplained data loss.

For a Senior DBA assessment, require **80/100 on Projects 8–10**, plus a live troubleshooting exercise. Setup success alone should not establish senior readiness.

## Trainer-Only Assessment Method

After the candidate demonstrates the working system, introduce one undisclosed fault from the project's trainer challenge. Allow 20–30 minutes to investigate.

Score whether they form a hypothesis, collect evidence, identify the cause, choose a safe correction, and verify recovery. Reward a justified decision to abort a risky operation.

Recovery and latency targets are **training objectives**, not AWS guarantees. Set them before each exercise, hold workload conditions consistent, and grade both the outcome and the candidate's explanation.

Feature support, restrictions, and pricing can change. Candidates must check the linked AWS documentation for their exact engine version and Regions before running each lab.

[Back to the training repository](../../README.md)
