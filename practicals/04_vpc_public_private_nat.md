# Practical 04 — Public/Private VPC + NAT Gateway

## Lab architecture

```text
                         INTERNET
                          /     \
                       IGW-A   IGW-B
                         |       |
                   +-----+---+ +--+------+
                   | VPC-A   | | VPC-B   |
                   |10.0.0/16| |20.0.0/16|
                   |         | |         |
                   | Public  | | Public  |
                   |10.0.1/24| |20.0.1/24|
                   | Private | | Private |
                   |10.0.2/24| |20.0.2/24|
                   +----+----+ +----+----+
                        |            |
                       NAT          NAT
```

## VPC-A

```text
VPC-A     = 10.0.0.0/16
Public-A  = 10.0.1.0/24   (ap-south-1a)
Private-A = 10.0.2.0/24   (ap-south-1b)
```

## Steps

1. Create VPC-A with `10.0.0.0/16`.
2. Create Public-A `10.0.1.0/24` and enable auto-assign public IPv4 for the public subnet lab.
3. Create Private-A `10.0.2.0/24` without public IPv4.
4. Create/attach IGW-A.
5. Public route table: `0.0.0.0/0 → IGW-A`.
6. Associate Public-A with the public route table.
7. Allocate an Elastic IP.
8. Create a public NAT Gateway in Public-A using the EIP.
9. Private route table: `0.0.0.0/0 → NAT-A`.
10. Associate Private-A with the private route table.
11. Launch a public EC2 with public IPv4 and a private EC2 without public IPv4.
12. Test public access and private outbound Internet.

## Private outbound test

From the private EC2:

```bash
curl -4 https://checkip.amazonaws.com
curl -I https://www.google.com
```

## NAT troubleshooting checklist

```text
Private route: 0.0.0.0/0 → NAT
→ NAT status Available
→ NAT in public subnet
→ NAT has EIP
→ public route: 0.0.0.0/0 → IGW
```
