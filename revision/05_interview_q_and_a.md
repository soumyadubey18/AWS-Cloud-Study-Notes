# 25 — AWS Interview Q&A

## 1. What is AWS?

**Small answer:** Amazon Web Services.

**Big answer:** AWS is Amazon's cloud platform providing compute, storage, networking, databases and many other services.

## 2. What is EC2?

**Small answer:** Elastic Compute Cloud — virtual servers.

**Big answer:** EC2 provides virtual servers called instances to run applications and workloads.

## 3. What is AMI?

**Small answer:** Amazon Machine Image — EC2 blueprint.

**Big answer:** An AMI is a template containing the OS image and base configuration used to launch EC2 instances.

## 4. What is SSH?

**Small answer:** Secure Shell.

**Big answer:** SSH provides secure remote command-line access to a server, commonly on TCP 22.

## 5. What is EBS?

**Small answer:** Elastic Block Store — block storage.

**Big answer:** EBS provides persistent block storage for EC2 and works like a disk attached to a server.

## 6. What is EFS?

**Small answer:** Elastic File System — shared file storage.

**Big answer:** EFS provides managed file storage that multiple Linux EC2 instances can mount and share.

## 7. What is S3?

**Small answer:** Simple Storage Service — object storage.

**Big answer:** S3 stores data as objects inside buckets.

## 8. What is a VPC?

**Small answer:** Virtual Private Cloud — an isolated AWS network.

**Big answer:** A VPC is a logically isolated virtual network where you create subnets, routes and security controls.

## 9. What makes a subnet public?

A route in the subnet's route table provides a path to an Internet Gateway.

## 10. Why NAT Gateway?

It lets private-subnet resources initiate outbound Internet connections without giving them public IPs.

## 11. SG vs NACL?

SG = stateful/resource-level/allow. NACL = stateless/subnet-level/allow+deny.

## 12. What is VPC Peering?

A private VPC-to-VPC network connection. Use non-overlapping CIDRs, an Active peering connection, routes on both sides, and appropriate security rules.

## 13. What is ALB?

Application Load Balancer, Layer 7, HTTP/HTTPS.

## 14. What is NLB?

Network Load Balancer, Layer 4, TCP/UDP.

## 15. What is a Target Group?

A group of backend targets such as EC2 instances that receive load-balanced traffic.

## 16. What is ASG?

Auto Scaling Group; it manages EC2 capacity according to configured capacity/scaling rules.

## 17. What is a Launch Template?

A reusable EC2 launch configuration — effectively the recipe for how to launch an instance.

## 18. What is CloudWatch?

AWS monitoring and observability service for metrics, logs, dashboards and alarms.

## 19. What is SNS?

Simple Notification Service; it sends messages/notifications to subscribers.

## 20. What is IAM?

Identity and Access Management; controls who can access AWS resources and what actions they can perform.

## 21. Why IAM Role for EC2?

To provide AWS permissions to EC2 without storing long-lived access keys directly on the instance.

## 22. What is RDS?

Relational Database Service — managed relational database.

## 23. Multi-AZ vs Read Replica?

Multi-AZ = mainly availability/failover. Read Replica = mainly read scaling.

## 24. What is DynamoDB?

AWS managed NoSQL database using tables, items and attributes.

## 25. Query vs Scan?

Query = targeted lookup. Scan = broader examination.

## How to answer during a blackout

Pause for 2–3 seconds and say:

> “Let me think about that for a moment.”

Then use:

**Full form → What it is → Why we use it → Example/flow**

If you do not remember the exact detail, do not invent it.
