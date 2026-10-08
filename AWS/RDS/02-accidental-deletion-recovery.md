# Task: Recover from accidental data deletion

**Difficulty:** Foundation+

**Suggested effort:** 6–8 hours

An operator deletes yesterday’s orders while new orders continue arriving.

## Objectives

- Restore missing data while preserving later valid transactions and measure the recovery outcome.

## Requirements

- Follow the [shared scenario, requirements, submission package, and scoring rubric](./README.md).
- Complete earlier projects or provide an equivalent working environment.

## Suggested Steps

1. Generate identifiable transactions and record their timestamps.
2. Perform a controlled deletion.
3. Restore to a point before deletion.
4. Recover the missing records while preserving valid transactions written afterward.
5. Test a separate snapshot restore and compare the recovery procedures.
6. Measure recovery time and identify any unrecoverable interval.

## Verification

Deleted orders are recovered without duplicating records or overwriting later valid transactions.

## Example Deliverable

Recovery runbook, incident timeline, reconciliation SQL, and before/after counts and order totals.

## Notes

**Trainer challenge:** The restored database is healthy, but the application cannot connect. Check whether the candidate verifies networking, credentials, and parameter groups.

PITR creates a new cluster, so selective recovery and application cutover require additional work.

- [AWS PITR documentation](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-pitr.html)

[Back to the project index](./README.md)
