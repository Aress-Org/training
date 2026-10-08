# Task: Diagnose and tune a slow order-processing workload

**Difficulty:** Intermediate

**Suggested effort:** 10–12 hours

Checkout latency increases during reporting activity.

## Objectives

- Diagnose bottlenecks using evidence and demonstrate improvement under equivalent workload conditions.

## Requirements

- Follow the [shared scenario, requirements, submission package, and scoring rubric](./README.md).
- Complete earlier projects or provide an equivalent working environment.

## Suggested Steps

1. Establish a baseline for throughput, p95 latency, errors, connections, and database load.
2. Diagnose three problems: a poorly indexed query, a blocking transaction, and inefficient reporting.
3. Use CloudWatch Database Insights, database logs, and execution plans to support the diagnosis.
4. Apply targeted fixes and rerun the same workload.
5. Move appropriate reporting traffic to readers and test freshness requirements.

## Verification

Improve the deliberately inefficient query’s p95 latency by at least 30% under equivalent test conditions, without incorrect results or increased errors.

## Example Deliverable

Before/after execution plans, monitoring evidence, SQL changes, and benchmark results.

## Notes

**Trainer challenge:** CPU is low while response times are high. The candidate must investigate waits and blocking.

Use CloudWatch Database Insights. The Aurora reader endpoint balances connections, not individual queries.

- [CloudWatch Database Insights](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Database-Insights.html)
- [AWS reader endpoint documentation](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Endpoints.Reader.html)

[Back to the project index](./README.md)
