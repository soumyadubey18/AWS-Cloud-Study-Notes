# AWS Interview Questions & Answer Pattern

## Answer Pattern
**Full form -> What it is -> Why we use it -> Example/flow**

## Core Questions

### What is EC2?
EC2 stands for Elastic Compute Cloud. It provides virtual servers in AWS.

### What is an AMI?
AMI stands for Amazon Machine Image. It is a preconfigured image/template used to launch EC2 instances.

### What is VPC?
VPC stands for Virtual Private Cloud. It is a logically isolated network in AWS.

### What makes a subnet public?
Its route table has a route to an Internet Gateway.

### Why use NAT Gateway?
It allows private-subnet resources to make outbound Internet connections without public IPs.

### What is VPC Peering?
A private network connection between two VPCs. Routes are needed on both sides and the CIDRs must not overlap.

### What is EBS?
Elastic Block Store; persistent block storage used with EC2.

### What is EFS?
Elastic File System; managed file storage designed for shared access.

### What is S3?
Simple Storage Service; object storage using buckets and objects.

### What is IAM Role for EC2?
An EC2 instance can assume an IAM Role to receive AWS permissions without storing long-lived access keys on the instance.

### ALB vs NLB?
ALB = Layer 7, HTTP/HTTPS. NLB = Layer 4, TCP/UDP.

### What is ASG?
Auto Scaling Group automatically manages the number of EC2 instances according to configured capacity/scaling rules.

### What is CloudWatch?
An AWS monitoring/observability service for metrics, logs, dashboards and alarms.

### What is RDS?
Relational Database Service; a managed relational database service.

### What is DynamoDB?
A managed NoSQL database using tables, items and attributes.
