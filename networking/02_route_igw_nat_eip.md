# 11 — Route Tables, IGW, NAT Gateway and Elastic IP

## Route Table

A route table contains rules that decide where network traffic should go.

**Memory:** Route Table = traffic road map.

## Typical public route

```text
0.0.0.0/0 → Internet Gateway
```

## Internet Gateway (IGW)

**IGW = Internet Gateway.** It provides the Internet path for appropriately routed public VPC resources.

**Memory:** IGW = Internet door.

## NAT Gateway

**NAT = Network Address Translation.** A NAT Gateway allows private-subnet resources to initiate outbound Internet connections without giving those resources public IPv4 addresses.

The trainer practical places the NAT Gateway in a **public subnet** and gives it an **Elastic IP**.

## Private Internet flow

```text
Private EC2
   ↓
Private Route Table
   ↓ 0.0.0.0/0 → NAT Gateway
NAT Gateway (Public Subnet + EIP)
   ↓
Public Route Table
   ↓ 0.0.0.0/0 → IGW
Internet
```

## NAT practical steps

1. Create/identify a public subnet.
2. Allocate an Elastic IP.
3. Create NAT Gateway in the public subnet.
4. Associate the EIP.
5. Wait until NAT status is **Available**.
6. Create/choose the private route table.
7. Add `0.0.0.0/0 → NAT Gateway`.
8. Associate the private route table with the private subnet.

## Public vs private route memory

```text
Public  → IGW
Private → NAT → IGW
```

## Elastic IP

**EIP = Elastic IP** in the training revision: a static public IPv4 address associated with a supported AWS resource.
