# Practical 05 — VPC Peering

## Goal

Connect two non-overlapping VPCs privately and verify communication using private IPs.

## Lab CIDRs

```text
VPC-A = 10.0.0.0/16
VPC-B = 20.0.0.0/16
```

## Steps

1. Create the two VPCs with non-overlapping CIDRs.
2. Create public/private subnets as required by the lab.
3. Create the peering connection: VPC-A → VPC-B.
4. Accept the peering request.
5. Wait for **Active** status.
6. VPC-A route table: `20.0.0.0/16 → VPC Peering Connection`.
7. VPC-B route table: `10.0.0.0/16 → VPC Peering Connection`.
8. Allow ICMP/required traffic in Security Groups/NACLs.
9. Test using the destination EC2's **private IP**.

## Memory

```text
Peering = Private VPC-to-VPC
Requirements = Non-overlap + Active + Routes both sides + Security rules
```

## Failure before peering

The trainer practical notes show that before peering, trying to reach the other VPC's private IP results in an unreachable path.

## Test after peering

From EC2-A:

```bash
ping <EC2-B-PRIVATE-IP>
```

A response such as `64 bytes from ...` confirms replies were received.
