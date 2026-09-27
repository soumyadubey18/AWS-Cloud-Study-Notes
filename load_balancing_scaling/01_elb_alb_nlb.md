# 14 — Load Balancing: ELB, ALB, NLB

## Load Balancer / ELB

**ELB = Elastic Load Balancing.** It distributes incoming traffic across backend targets and uses health checks to direct traffic to healthy targets.

**Memory:** Load Balancer = distribute traffic.

## Target Group

A Target Group contains backend targets such as EC2 instances that receive traffic forwarded by the Load Balancer.

**Memory:** Target Group = Backend servers.

## Listener

A listener accepts connections/requests on a configured port. The training revision commonly uses:

- Port 80 — HTTP
- Port 443 — HTTPS

## Health Check

A Health Check checks whether a registered target is healthy and able to receive traffic. Unhealthy targets are normally not sent regular traffic.

**Memory:** Health Check = Is backend healthy?

## ALB

**ALB = Application Load Balancer.** It works at **Layer 7** and is designed for **HTTP/HTTPS** traffic. The training material references application-aware routing such as URL path or host-based routing.

**Memory:** ALB = L7 + HTTP/HTTPS.

## NLB

**NLB = Network Load Balancer.** It works at **Layer 4** and handles connections such as **TCP/UDP**, with a focus on high performance and low latency.

**Memory:** NLB = L4 + TCP/UDP.

## ALB vs NLB

| ALB | NLB |
|---|---|
| Layer 7 | Layer 4 |
| HTTP/HTTPS | TCP/UDP |
| Application-aware routing | Network-level connections |

## Traffic flow

```text
User
 ↓
Load Balancer
 ↓
Listener
 ↓
Target Group
 ↓
Healthy EC2 targets
```
