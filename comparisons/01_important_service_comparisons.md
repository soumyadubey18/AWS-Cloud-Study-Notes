# Important AWS Service Comparisons

| Comparison | Key difference | Memory |
|---|---|---|
| EC2 vs AMI | EC2 is the virtual server; AMI is the launch template/image | Server vs Blueprint |
| EBS vs EFS | EBS is block storage; EFS is shared file storage | Block vs File |
| EBS vs S3 | EBS is block storage for compute; S3 is object storage | Block vs Object |
| SG vs NACL | SG is stateful and resource/ENI-level; NACL is stateless and subnet-level | Stateful vs Stateless |
| ALB vs NLB | ALB is Layer 7 for HTTP/HTTPS; NLB is Layer 4 for TCP/UDP | L7 vs L4 |
| Launch Template vs ASG | Launch Template stores launch settings; ASG manages instance count | How vs How many |
| CloudWatch vs SNS | CloudWatch monitors/detects; SNS sends notifications | Monitor vs Notify |
| Multi-AZ vs Read Replica | Multi-AZ is mainly availability/failover; Read Replica is mainly read scaling | Availability vs Reads |
| RDS vs DynamoDB | RDS is managed relational SQL; DynamoDB is managed NoSQL | SQL vs NoSQL |
| Public vs Private Subnet | Public has route to IGW; private has no direct IGW route for general Internet access | IGW vs no direct IGW |
