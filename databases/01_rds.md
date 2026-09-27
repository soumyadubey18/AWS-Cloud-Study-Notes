# 19 — RDS (Relational Database Service)

## What is RDS?

**RDS = Relational Database Service.** It is AWS's managed relational database service.

**Memory:** RDS = Managed Relational / SQL Database.

## Database examples from the training material

- MySQL
- PostgreSQL
- MariaDB

## Common ports in the revision

- MySQL — 3306
- PostgreSQL — 5432
- SQL Server — 1433
- Oracle — 1521

## Multi-AZ

The training revision describes Multi-AZ mainly for **high availability and failover**, using another Availability Zone for standby/failover support.

**Memory:** Multi-AZ = Availability.

## Read Replica

A Read Replica is a copy used mainly to **scale read workloads** and offload read traffic.

**Memory:** Replica = Read scaling.

## Multi-AZ vs Read Replica

| Multi-AZ | Read Replica |
|---|---|
| Mainly high availability/failover | Mainly read scaling |

## EC2 cannot connect to RDS — check

```text
RDS status
→ endpoint
→ port 3306 (for MySQL)
→ Security Group source/rules
→ network connectivity
→ database credentials
```

The trainer practical also shows an RDS Security Group rule allowing 3306 from the EC2 Security Group when MySQL is used.
