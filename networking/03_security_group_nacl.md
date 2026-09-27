# 12 — Security Group and NACL

## Security Group (SG)

A Security Group is a **stateful virtual firewall** for a resource/network interface.

Trainer memory line:

**SG = Stateful + Resource/ENI + Allow rules.**

Common lab ports:

- SSH: 22
- HTTP: 80
- HTTPS: 443
- RDP: 3389
- MySQL: 3306
- PostgreSQL: 5432
- NFS/EFS: 2049

## NACL

**NACL = Network Access Control List.** It is a **stateless firewall at the subnet level**.

Trainer memory line:

**NACL = Stateless + Subnet + Allow/Deny.**

## Stateful vs stateless

- **Stateful:** return traffic for an allowed connection is automatically allowed.
- **Stateless:** return traffic must be explicitly allowed by the appropriate rule.

## SG vs NACL

| Security Group | NACL |
|---|---|
| Resource / ENI level | Subnet level |
| Stateful | Stateless |
| Allow rules | Allow + Deny rules |

**Memory:** SG = Stateful instance/resource firewall. NACL = Stateless subnet firewall.
