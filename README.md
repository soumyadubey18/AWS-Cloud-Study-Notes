# AWS Study Notes — Topic Wise

This repository contains **AWS-only learning notes, practicals, interview revision, commands, flows, and memory lines** collected from Soumya's AWS training material and the AWS mock-revision material prepared during study.

## What is included

- AWS & Cloud Basics
- AWS Global Infrastructure: Region, Availability Zone, Edge/Local Zone
- EC2: instances, AMI, instance types, purchasing options, key pair, public/private IP, Elastic IP, SSH, User Data, lifecycle
- EBS: block storage, snapshot, attach/format/mount/detach practical
- EFS: shared file storage, NFS, mount, multi-EC2 practical
- S3: bucket, object, versioning, archive/Glacier, static website, AWS CLI practical
- IAM: users, groups, roles, policies, EC2 IAM role
- VPC: CIDR, subnets, public/private, route tables, IGW, NAT Gateway, Elastic IP, Security Groups, NACLs
- VPC Peering and S3 Gateway Endpoint
- Load Balancing: ELB, ALB, NLB, Target Groups, Listeners, Health Checks
- Auto Scaling: Launch Template, ASG, Min/Desired/Max, scaling flow
- CloudWatch and SNS
- RDS: relational DB, MySQL/PostgreSQL, Multi-AZ, Read Replica
- DynamoDB: table, item, attribute, partition key, sort key, composite key, Query vs Scan
- CloudTrail basics from revision material
- Full forms, ports, comparisons, troubleshooting and interview answers

## Deliberately excluded

This repository is limited to **AWS topics**. Separate Linux, Python, Git/GitHub, Docker, Ansible and Terraform study material is not included as standalone topics.

AWS practical commands are included where they are part of an AWS lab (for example, SSH for EC2, filesystem commands for EBS/EFS, and AWS CLI commands for S3).

## Suggested GitHub layout

```text
AWS_Study_Notes_Git/
├── README.md
├── fundamentals/
├── ec2/
├── storage/
├── networking/
├── load_balancing_scaling/
├── monitoring_notifications/
├── databases/
├── practicals/
└── revision/
```

## Core memory map

```text
EC2  = Virtual Server
AMI  = Blueprint
EBS  = Block / Disk
EFS  = Shared File
S3   = Object Storage
VPC  = AWS Network
SG   = Stateful Firewall
NACL = Stateless Firewall
IGW  = Internet Path
NAT  = Private Outbound Internet Path
ALB  = Layer 7 / HTTP-HTTPS
NLB  = Layer 4 / TCP-UDP
ASG  = EC2 Count Management
Launch Template = How to launch
CloudWatch = Monitor
SNS = Notify
RDS = Managed Relational Database
DynamoDB = Managed NoSQL Database
```

## AWS networking flows

```text
Public EC2  → Route Table → IGW → Internet
Private EC2 → Route Table → NAT Gateway → IGW → Internet
VPC A       → VPC Peering → VPC B
Private EC2 → S3 Gateway Endpoint → S3
```

## Study answer pattern

**Full form → What it is → Why we use it → Simple example/flow → Key difference (when asked)**
