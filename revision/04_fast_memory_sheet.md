# 24 — Fast AWS Memory Sheet

## Core

```text
AWS  = Amazon Web Services
EC2  = Virtual Server
AMI  = Blueprint
EBS  = Block
EFS  = File
S3   = Object
VPC  = Network
SG   = Stateful
NACL = Stateless
IGW  = Internet path
NAT  = Private outbound Internet
ALB  = L7 / HTTP-HTTPS
NLB  = L4 / TCP-UDP
ASG  = Add/remove EC2
CloudWatch = Monitor
SNS = Notify
RDS = Managed relational DB
DynamoDB = NoSQL
```

## Flows

```text
Public  → Route Table → IGW → Internet
Private → Route Table → NAT → IGW → Internet
Peering → Private VPC-to-VPC + routes on both sides
EC2 → IAM Role → AWS service
High CPU → CloudWatch → Alarm → SNS
Launch Template → ASG → EC2
User → ELB → Target Group → Healthy EC2
```

## Storage memory

**EBS = Block | EFS = File | S3 = Object**

## Database memory

**Multi-AZ = Availability | Read Replica = Reads**

**RDS = Relational | DynamoDB = NoSQL**

## DynamoDB memory

**Partition Key + Sort Key = Composite Key**

**Query = Targeted | Scan = Broad**

## Ports

**22 | 80 | 443 | 3306 | 5432 | 3389 | 2049**
