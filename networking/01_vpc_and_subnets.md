# 10 — VPC, CIDR and Subnets

## VPC

**VPC = Virtual Private Cloud.** It is a logically isolated virtual network in AWS where subnets, routes and security controls are configured.

**Remember:** VPC = AWS Network.

## VPC types in the trainer material

### Default VPC

Created in each AWS Region for an account. The training notes describe default networking resources and Internet connectivity as part of the default setup.

### Custom VPC

A VPC created by the account owner where the CIDR and required networking components are chosen.

## CIDR

CIDR defines the network IP range.

Trainer examples:

```text
VPC-A: 10.0.0.0/16
Public-A: 10.0.1.0/24
Private-A: 10.0.2.0/24

VPC-B: 20.0.0.0/16
Public-B: 20.0.1.0/24
Private-B: 20.0.2.0/24
```

The VPC training notes describe the allowed VPC IPv4 block as `/16` to `/28`.

## Subnet

A subnet is a smaller network range inside a VPC and is associated with an Availability Zone.

## Public subnet

A subnet whose route table has a route to an Internet Gateway.

For IPv4 Internet communication, the instance also needs appropriate public addressing such as a public IPv4 address or Elastic IP, together with the necessary security/routing configuration.

**Remember:** Public subnet = route to IGW.

## Private subnet

A subnet without a direct route to an Internet Gateway. It can use a NAT Gateway for outbound Internet access.

**Remember:** Private = no direct IGW route; outbound → NAT.

## AWS-reserved subnet addresses — trainer example

For `10.0.0.0/24`, the trainer notes list five reserved addresses:

- `10.0.0.0` — network address
- `10.0.0.1` — VPC router
- `10.0.0.2` — DNS server
- `10.0.0.3` — future use
- `10.0.0.255` — broadcast address reserved by AWS

Trainer calculation: `256 - 5 = 251` usable addresses in that `/24` example.
