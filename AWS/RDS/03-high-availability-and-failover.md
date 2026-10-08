# Task: Prove high availability from the application’s perspective

**Difficulty:** Intermediate

**Suggested effort:** 8–10 hours

Orders must continue processing when the writer changes.

## Objectives

- Measure end-to-end failover behavior and preserve transaction correctness during recovery.

## Requirements

- Follow the [shared scenario, requirements, submission package, and scoring rubric](./README.md).
- Complete earlier projects or provide an equivalent working environment.

## Suggested Steps

1. Configure and explain replica promotion priorities.
2. Run continuous reads and writes with unique transaction identifiers.
3. Trigger controlled cluster failovers three times.
4. Measure database promotion time separately from application recovery time.
5. Investigate connection pools, DNS behavior, timeouts, and retry handling.
6. Reconcile successful, failed, and ambiguous transactions after each test.

## Verification

The application reconnects without manually changing the writer hostname; acknowledged transactions reconcile; retries do not create duplicate orders.

## Example Deliverable

Failover timeline, application logs, transaction reconciliation, and a recovery runbook.

## Notes

**Trainer challenge:** Use a client that holds stale connections.

Senior-level distinction: explain how Aurora’s storage resilience differs from compute failover readiness.

- [AWS Aurora resilience documentation](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/disaster-recovery-resiliency.html)

[Back to the project index](./README.md)
