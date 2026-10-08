# Task: Build a production-style Aurora foundation

**Difficulty:** Foundation

**Suggested effort:** 4–6 hours

The retailer is launching its first AWS-hosted database.

## Objectives

- Deploy a reproducible, private Aurora environment and understand its configuration and endpoints.

## Requirements

- Follow the [shared scenario, requirements, submission package, and scoring rubric](./README.md).
- Complete earlier projects or provide an equivalent working environment.

## Suggested Steps

1. Create a VPC, private database subnets, security groups, and an Aurora cluster with a writer and a reader in different Availability Zones.
2. Configure backup retention, maintenance windows, and parameter groups.
3. Connect from a private client through an approved access path.
4. Load the sample schema and demonstrate writer, reader, and instance endpoints.
5. Recreate the environment from the submitted infrastructure definition.

## Verification

Authorized clients connect successfully; unauthorized clients fail; application privileges are restricted; deployment is reproducible.

## Example Deliverable

Architecture diagram, deployment files, connectivity tests, and a short explanation of cluster-level versus instance-level settings.

## Notes

**Trainer challenge:** Introduce an incorrect security-group rule. Ask the candidate to diagnose the connection failure without making the database public.

[Back to the project index](./README.md)
