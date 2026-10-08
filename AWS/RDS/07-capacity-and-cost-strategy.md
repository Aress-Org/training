# Task: Choose an Aurora capacity and cost strategy

**Difficulty:** Advanced

**Suggested effort:** 10–12 hours

The retailer has idle periods, steady daytime demand, and sudden peaks.

## Objectives

- Choose a capacity configuration using measured performance and a complete cost estimate.

## Requirements

- Follow the [shared scenario, requirements, submission package, and scoring rubric](./README.md).
- Complete earlier projects or provide an equivalent working environment.

## Suggested Steps

1. Replay idle, steady, and burst workload profiles.
2. Compare a provisioned configuration with Aurora Serverless v2.
3. Test different minimum and maximum ACU settings.
4. Where supported, demonstrate auto-pause and measure resume latency.
5. Model Aurora Standard versus I/O-Optimized using observed usage and current regional prices.
6. Include readers, storage, backups, monitoring, proxy, and networking in the estimate.

## Verification

Select the lowest estimated cost configuration that meets the declared latency and availability requirements. Label extrapolated costs clearly.

## Example Deliverable

Performance/cost comparison, assumptions, and separate recommendations for development and production.

## Notes

**Trainer challenge:** Persistent connections prevent an expected pause, or burst latency increases despite available maximum capacity.

Auto-pause depends on version and feature compatibility; paused compute does not eliminate all charges.

- [AWS auto-pause guidance](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-serverless-v2-auto-pause.html)
- [Current Aurora pricing](https://aws.amazon.com/rds/aurora/pricing/)

[Back to the project index](./README.md)
