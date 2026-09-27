# 13 — VPC Peering and S3 Gateway Endpoint

## VPC Peering

VPC Peering creates a **private network connection between two VPCs** so resources can communicate using private IPs, subject to routing and security controls.

**Memory:** Peering = private VPC-to-VPC.

## Requirements from the training material

1. VPC CIDRs must **not overlap**.
2. Create the peering connection.
3. Accept the request.
4. Wait for **Active** status.
5. Add routes to the opposite VPC CIDR on **both sides**.
6. Allow the required traffic in Security Groups/NACLs.
7. Test using the other VPC's private IP.

## Trainer examples

One practical uses:

```text
VPC-A = 10.0.0.0/16
VPC-B = 20.0.0.0/16
```

The trainer exam revision also shows another example using:

```text
VPC-A = 10.0.0.0/16
VPC-B = 192.168.0.0/16
```

The important point is that the CIDRs do not overlap.

## Peering route example

```text
VPC-A route: 20.0.0.0/16 → VPC Peering Connection
VPC-B route: 10.0.0.0/16 → VPC Peering Connection
```

## Is IGW required for peering?

No. VPC peering is private VPC-to-VPC connectivity.

## Is peering transitive?

No. If A peers with B and B peers with C, A does not automatically communicate with C through B.

## Inter-Region peering

The trainer revision states that VPC peering can work across Regions.

## S3 Gateway VPC Endpoint

An S3 Gateway Endpoint provides private-subnet access to S3 without requiring a NAT Gateway for that S3 traffic.

Trainer flow:

```text
VPC → Endpoints → Create endpoint
Service category: AWS services
Service: com.amazonaws.<region>.s3
Type: Gateway
VPC: VPC-A
Route table: Private-RT-A
```

Then test from the private EC2 with AWS CLI commands such as:

```bash
aws s3 ls
aws s3 cp test.txt s3://YOUR-BUCKET-NAME/
```

**Memory:** Private EC2 → S3 Gateway Endpoint → S3.
