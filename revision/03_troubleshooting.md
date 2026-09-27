# 23 — AWS Troubleshooting Playbook

## General sequence

Use this sequence for AWS interview troubleshooting:

1. Is the resource running?
2. Is the required application/service running?
3. Is the required port correct/open?
4. Are Security Group and NACL rules correct?
5. Is the route table/network path correct?
6. Check logs and CloudWatch metrics.
7. Make the change.
8. Test again and confirm.

## Website not opening through EC2 public IP

```text
EC2 state
→ Apache/httpd
→ Port 80
→ Security Group
→ Public IP
→ Route table
→ IGW
→ curl localhost
```

## Private EC2 cannot access Internet

```text
Private route
→ NAT Gateway
→ NAT in public subnet
→ EIP
→ Public route
→ IGW
```

## VPC Peering is active but ping fails

```text
Non-overlapping CIDRs
→ peering Active
→ routes BOTH sides
→ ICMP/security rules
→ correct private IP
```

## ALB target is unhealthy

```text
Application running
→ correct target port
→ health-check path
→ target SG
→ ALB-to-target connectivity
```

## EC2 cannot connect to RDS

```text
RDS status
→ endpoint
→ DB port
→ SG source
→ network
→ credentials
```

## ASG not scaling

```text
Min/Desired/Max
→ Launch Template
→ scaling policy
→ CloudWatch metric/alarm
→ instance/subnet readiness
```

## SNS email not received

```text
Topic
→ subscription exists
→ subscription confirmed
→ alarm action
→ endpoint
```

## S3 CLI cannot authenticate

`aws sts get-caller-identity` and then check the EC2 IAM Role / CLI authentication method.

## S3 `AccessDenied`

Check IAM permissions and S3 bucket policy.
