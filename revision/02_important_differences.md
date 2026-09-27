# 22 — Important AWS Differences

## EC2 vs AMI

- EC2 = actual virtual server.
- AMI = blueprint used to launch EC2.

## EBS vs EFS

- EBS = block/disk storage.
- EFS = shared file storage.

## EBS vs S3

- EBS = block storage for EC2.
- S3 = object storage.

## Public vs Private Subnet

- Public subnet = route to IGW.
- Private subnet = no direct IGW route; can use NAT for outbound Internet.

## IGW vs NAT

- IGW = Internet path for public routing.
- NAT = private outbound Internet path through the public path.

## Security Group vs NACL

- SG = stateful, resource/ENI level, allow rules.
- NACL = stateless, subnet level, allow/deny.

## ALB vs NLB

- ALB = Layer 7, HTTP/HTTPS.
- NLB = Layer 4, TCP/UDP.

## Launch Template vs ASG

- Launch Template = how to launch.
- ASG = how many to run/manage.

## CloudWatch vs SNS

- CloudWatch = monitor/detect.
- SNS = notify.

## Multi-AZ vs Read Replica

- Multi-AZ = availability/failover.
- Read Replica = read scaling.

## RDS vs DynamoDB

- RDS = managed relational SQL database.
- DynamoDB = managed NoSQL database.

## CloudWatch vs CloudTrail

- CloudWatch = monitoring/metrics/logs/alarms.
- CloudTrail = API activity/audit records.
