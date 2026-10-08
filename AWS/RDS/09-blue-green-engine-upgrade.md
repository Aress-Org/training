# Task: Upgrade Aurora with a controlled Blue/Green deployment

**Difficulty:** Expert

**Suggested effort:** 10–14 hours

The database needs an engine upgrade without an extended maintenance outage.

## Objectives

- Rehearse a compatible Blue/Green upgrade and prove application, performance, and recovery readiness.

## Requirements

- Follow the [shared scenario, requirements, submission package, and scoring rubric](./README.md).
- Complete earlier projects or provide an equivalent working environment.

## Suggested Steps

1. Verify support for the exact source version, target version, Region, and enabled features.
2. Build a compatible Blue/Green lab environment.
3. Run extension, schema, application, and query-performance checks.
4. Monitor replication and enforce change restrictions during the rehearsal.
5. Perform a switchover and measure application interruption.
6. Define abort criteria, backup coverage, and recovery after production writes reach green.

## Verification

Data reconciles, application tests pass, and performance meets the agreed threshold. Explain why reverting to old blue after new writes requires reconciliation.

## Example Deliverable

Compatibility checklist, change plan, test results, and post-upgrade recovery procedure.

## Notes

**Trainer challenge:** Present a feature combination that prevents the proposed deployment.

Check credential-management restrictions explicitly: Blue/Green currently does not support RDS-managed master passwords through Secrets Manager. Use a documented compatible credential design for this lab. Verify current restrictions before deployment.

- [AWS Blue/Green limitations](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/blue-green-deployments-considerations.html)

[Back to the project index](./README.md)
