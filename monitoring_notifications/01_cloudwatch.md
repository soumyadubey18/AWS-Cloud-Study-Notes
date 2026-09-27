# 16 — CloudWatch

## What is CloudWatch?

CloudWatch is an AWS monitoring and observability service used for **metrics, logs, dashboards and alarms**.

**Memory:** CloudWatch = Monitor.

## Metric

A metric is a measurable value such as EC2 CPU utilization or network activity.

## Alarm

An alarm watches a metric and can trigger an action when a threshold is reached.

Example:

```text
CPU utilization high
      ↓
CloudWatch metric
      ↓
Alarm reaches threshold
      ↓
Action
```

## Alarm states in the revision

- OK
- ALARM
- INSUFFICIENT_DATA

## Common uses from the training material

- Monitor EC2 CPU/network metrics.
- Trigger Auto Scaling actions.
- Trigger SNS notifications.
- View metrics on dashboards.
- Troubleshoot systems with metrics/logs.
