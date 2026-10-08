# Task: Survive a connection storm with RDS Proxy

**Difficulty:** Advanced

**Suggested effort:** 8–10 hours

A flash sale causes connection exhaustion.

## Objectives

- Evaluate RDS Proxy under load, diagnose session pinning, and preserve correctness during overload.

## Requirements

- Follow the [shared scenario, requirements, submission package, and scoring rubric](./README.md).
- Complete earlier projects or provide an equivalent working environment.

## Suggested Steps

1. Generate bursts of short-lived client connections.
2. Benchmark direct connections against RDS Proxy under equivalent conditions.
3. Measure client connections, backend connections, connection latency, errors, and session pinning.
4. Introduce a documented pinning condition for the selected engine and demonstrate its impact.
5. Tune connection handling and repeat a writer failover test.

## Verification

Explain measured behavior, including any benefit limits. Preserve transaction correctness during overload and failover.

## Example Deliverable

Benchmark scripts, proxy configuration, metric comparisons, and a recommendation on whether the proxy is justified.

## Notes

**Trainer challenge:** The proxy is present, but backend connections remain unexpectedly high.

Pinning behavior depends on engine and session operations.

- [AWS RDS Proxy pinning documentation](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/rds-proxy-pinning.html)

[Back to the project index](./README.md)
