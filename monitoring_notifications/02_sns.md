# 17 — SNS (Simple Notification Service)

## What is SNS?

**SNS = Simple Notification Service.** It sends messages/notifications to subscribers.

**Memory:** SNS = Notify.

## Key terms

- **Topic:** communication channel.
- **Publisher:** sends/publishes the message.
- **Subscriber:** endpoint that receives the notification.

The training revision lists common endpoints such as Email, SMS, Lambda, SQS and HTTP/HTTPS.

## CloudWatch + SNS flow

```text
High CPU
  ↓
CloudWatch Metric
  ↓
CloudWatch Alarm
  ↓
SNS Topic
  ↓
Subscriber / Email / Notification
```

## Troubleshooting: SNS email not received

Training answer flow:

```text
Topic
→ subscription exists
→ subscription confirmed
→ alarm action
→ notification endpoint
```
