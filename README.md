# AWS Cloud Study Notes & Hands-On Labs

Beginner-friendly AWS study notes and practical labs based on my AWS learning journey.

## AWS Services Covered
- EC2, AMI, EBS, EFS, S3
- IAM
- VPC, Subnets, Route Tables, Internet Gateway, NAT Gateway, Elastic IP
- Security Groups, NACLs, VPC Peering, VPC Endpoints
- ELB, ALB, NLB, Target Groups, Health Checks
- Launch Templates, Auto Scaling
- CloudWatch, SNS, CloudTrail
- RDS, DynamoDB

## Repository Sections
| Folder | Purpose |
|---|---|
| `fundamentals/` | AWS and cloud foundations |
| `ec2/` | EC2, AMI, launching Linux/Windows instances |
| `storage/` | EBS, EFS, S3 |
| `networking/` | VPC and networking concepts |
| `load_balancing_scaling/` | ELB/ALB/NLB and Auto Scaling |
| `monitoring_notifications/` | CloudWatch, SNS, CloudTrail |
| `databases/` | RDS and DynamoDB |
| `practicals/` | Hands-on step-by-step labs |
| `architecture/` | Mermaid architecture diagrams |
| `cheatsheets/` | Commands and ports |
| `comparisons/` | Important AWS service differences |
| `troubleshooting/` | Common troubleshooting flows |
| `interview/` | Interview questions and answer patterns |
| `revision/` | Quick revision and memory sheets |

## Hands-On Labs Included
- Linux EC2 launch and SSH
- Windows EC2 launch and RDP
- Apache web server on EC2
- EBS attach, format, mount, unmount and detach
- EFS shared storage across EC2 instances
- Public/private VPC with NAT Gateway
- VPC Peering using private IP connectivity
- S3 CLI operations and S3 Gateway Endpoint
- DynamoDB `Students` table
- Custom AMI workflow

## Architecture Flow
Typical flows practiced in this repository:

```text
Public EC2 -> Route Table -> IGW -> Internet
Private EC2 -> Route Table -> NAT Gateway -> IGW -> Internet
User -> ALB/NLB -> Target Group -> Healthy EC2
Launch Template -> ASG -> EC2
EC2 Metric -> CloudWatch Alarm -> SNS -> Notification
VPC-A -> Peering -> VPC-B
```

## Security Note
Never commit AWS access keys, secret keys, session tokens, `.pem`/`.ppk` private keys, passwords, or other credentials.
