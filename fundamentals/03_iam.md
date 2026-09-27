# 09 — IAM (Identity and Access Management)

## What is IAM?

**IAM = Identity and Access Management.** IAM controls who can access AWS resources and what actions they can perform.

**Remember:** IAM = Who can do what.

## User vs Group vs Role vs Policy

| IAM component | Simple meaning |
|---|---|
| User | Identity |
| Group | Collection of users |
| Role | Assumable identity/permission set |
| Policy | JSON permission rules |

## Policy basics

The trainer revision describes a policy as a JSON document using elements such as **Effect, Action and Resource**.

## IAM Role for EC2

An EC2 instance can assume an IAM Role and receive permissions through attached policies. This avoids storing long-lived access keys directly on the instance for AWS access.

**Memory:** EC2 → Role → AWS service.

## AWS CLI identity check

```bash
aws sts get-caller-identity
```

This shows the AWS identity currently used by the CLI.

## Troubleshooting AccessDenied

First check which identity/role is being used, then inspect the relevant IAM permissions/policy.
