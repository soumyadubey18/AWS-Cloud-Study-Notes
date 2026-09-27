# AWS Troubleshooting Flows

## Website is not opening
1. Check EC2 state.
2. Check Apache/httpd status and whether it is listening.
3. Check port 80.
4. Check Security Group.
5. Check public IP and route table/IGW.
6. Test locally with `curl http://localhost`.
7. Check OS/network controls and logs.
8. Fix and retest.

## Private EC2 cannot access Internet
```text
Private Route Table -> NAT Gateway -> Public Subnet -> Elastic IP -> IGW -> Internet
```
Check the private route, NAT state/subnet, Elastic IP, public route and security controls.

## VPC Peering is active but ping fails
Check non-overlapping CIDRs -> active peering -> routes on BOTH sides -> ICMP/security rules -> correct private IP.

## ALB target is unhealthy
Check application -> listener/target port -> health-check path -> target Security Group -> ALB-to-target connectivity.

## EC2 cannot connect to RDS
Check RDS status -> endpoint -> port 3306 (for MySQL) -> Security Group -> network path -> credentials.

## ASG is not scaling
Check Min/Desired/Max -> Launch Template -> scaling policy -> CloudWatch metric/alarm -> subnets/instance launch.

## SNS email not received
Check topic -> subscription -> confirmation -> alarm action -> notification endpoint.
