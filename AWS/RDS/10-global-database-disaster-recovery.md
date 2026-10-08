# Task: Design and operate cross-Region disaster recovery

**Difficulty:** Senior DBA capstone

**Suggested effort:** 16–20 hours

The retailer must recover service in a second AWS Region.

## Objectives

- Prove end-to-end cross-Region recovery, transaction reconciliation, and executable failback procedures.

## Requirements

- Follow the [shared scenario, requirements, submission package, and scoring rubric](./README.md).
- Complete earlier projects or provide an equivalent working environment.
- A second AWS Region and a usable secondary-region database instance are required. Check Global Database support for the selected engine version and Regions.

## Suggested Steps

1. Build an Aurora Global Database with a usable secondary-region database instance.
2. Prepare application access, credentials, networking, encryption permissions, and monitoring in both Regions.
3. Maintain an independent record of acknowledged application transactions.
4. Execute a planned switchover.
5. Separately rehearse an unplanned-failover decision using a controlled loss of application access to the primary. Identify the limits of this simulation.
6. Measure end-to-end recovery time and reconcile transaction loss.
7. Demonstrate failback and prevent application writes to the former primary during recovery.
8. Compare Global Database with a lower-cost cross-Region snapshot recovery design.

## Verification

A colleague can execute the runbook. Measure recovery through successful application transactions and report data loss honestly.

## Example Deliverable

Architecture, DR runbook, exercise evidence, transaction reconciliation, failback plan, and cost comparison.

## Notes

**Trainer challenge:** The secondary database is available, but an application dependency exists only in the primary Region.

A healthy planned switchover synchronizes the target before promotion; unplanned failover can lose transactions because cross-Region replication is asynchronous.

- [AWS Global Database recovery guidance](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-global-database-disaster-recovery.html)

[Back to the project index](./README.md)
