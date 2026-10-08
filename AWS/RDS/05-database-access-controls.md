# Task: Implement and test database access controls

**Difficulty:** Intermediate+

**Suggested effort:** 8–10 hours

Developers, reporting users, and operators need different access.

## Objectives

- Implement least privilege, secure authentication, credential rotation, and verifiable audit coverage.

## Requirements

- Follow the [shared scenario, requirements, submission package, and scoring rubric](./README.md).
- Complete earlier projects or provide an equivalent working environment.

## Suggested Steps

1. Create separate application, reporting, deployment, and administrative roles.
2. Configure IAM database authentication for an appropriate operational user.
3. Implement Secrets Manager rotation for a password-authenticated application user.
4. Enforce certificate-validated TLS.
5. Configure appropriate database audit logging and CloudTrail coverage for AWS management actions.
6. Demonstrate that IAM permissions and SQL privileges solve different access problems.

## Verification

Reporting users cannot modify orders; application users cannot administer the database; credential rotation preserves application operation; restricted actions fail.

## Example Deliverable

Access matrix, policies, grants, rotation results, and positive and negative access tests.

## Notes

**Trainer challenge:** Give a user permission to describe the cluster but no database login permissions.

- [IAM database accounts](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/UsingWithRDS.IAMDBAuth.DBAccounts.html)
- [Secrets Manager rotation](https://docs.aws.amazon.com/secretsmanager/latest/userguide/rotate-secrets_turn-on-for-db.html)

[Back to the project index](./README.md)
