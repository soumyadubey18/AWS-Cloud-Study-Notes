# 15 — Auto Scaling and Launch Template

## Auto Scaling Group (ASG)

**ASG = Auto Scaling Group.** It manages the number of EC2 instances according to configured capacity and scaling policies.

**Memory:** ASG = add/remove EC2.

## Minimum, Desired, Maximum

- **Minimum:** lowest number of instances allowed.
- **Desired:** number of instances ASG tries to maintain.
- **Maximum:** highest number of instances allowed.

Example from the revision:

```text
Min = 2
Desired = 3
Max = 6
```

## Launch Template

A Launch Template stores EC2 launch configuration such as:

- AMI
- Instance type
- Key pair
- Security Group
- Storage
- IAM role
- User Data

**Memory:** Launch Template = HOW to launch.

## Launch Template vs ASG

- **Launch Template:** how to launch.
- **ASG:** how many to run/manage.

## Relationship

```text
Launch Template
       ↓
Auto Scaling Group
       ↓
EC2 instances
```

## Scaling relationship with CloudWatch

The training revision uses the flow:

```text
EC2 metric → CloudWatch → Alarm → scaling action → ASG → EC2
```
