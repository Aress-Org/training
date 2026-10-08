# Task: Migrate a live PostgreSQL database into Aurora

**Difficulty:** Advanced+

**Suggested effort:** 12–16 hours

A self-managed PostgreSQL database must move to Aurora with a short write interruption.

## Objectives

- Plan, validate, and rehearse a live migration with explicit cutover and rollback boundaries.

## Requirements

- Follow the [shared scenario, requirements, submission package, and scoring rubric](./README.md).
- Complete earlier projects or provide an equivalent working environment.
- This brief uses PostgreSQL. For an Aurora MySQL track, use a MySQL source and document its engine-specific migration prerequisites.

## Suggested Steps

1. Build a source database and maintain continuous writes.
2. Assess extensions, privileges, data types, schema objects, and replication prerequisites.
3. Use AWS DMS full load plus change data capture.
4. Migrate and verify objects that the selected migration method does not transfer automatically.
5. Monitor replication lag and validate data.
6. Rehearse a cutover, including stopping source writes, draining changes, reconciling data, and switching the application.
7. Define rollback before and after target writes begin.

## Verification

No unexplained data discrepancies; measured write interruption meets the declared target; sequences and application operations work after migration.

## Example Deliverable

Compatibility assessment, migration configuration, validation results, and a timestamped cutover runbook.

## Notes

**Trainer challenge:** Introduce a table without a primary key or an incompatible extension.

Use AWS DMS validation, supplemented by business-level reconciliation.

- [AWS DMS validation](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Validating.html)

[Back to the project index](./README.md)
