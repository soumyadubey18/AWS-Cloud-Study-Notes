# Practical 07 — DynamoDB Students Table

## Table setup from the trainer lab

| Setting | Value |
|---|---|
| Table name | Students |
| Partition key | RollNo |
| Type | String |
| Sort key | SchoolYear |
| Type | Number |
| Capacity | On-Demand |

## Create table

1. AWS Console → DynamoDB.
2. Choose the lab Region, e.g. `ap-south-1`.
3. Tables → Create table.
4. Enter `Students`.
5. Partition key = `RollNo` / String.
6. Add sort key = `SchoolYear` / Number.
7. Use default table settings for the beginner lab.
8. Create the table.
9. Wait for status **Active**.

## First item

```text
RollNo     = 01
SchoolYear = 2026
Name       = Bhupinder
```

## Second item

```text
RollNo     = 02
SchoolYear = 2026
FavColor   = Red
```

## Key learning

The primary key is the combination `RollNo + SchoolYear`.

The lab demonstrates that non-key attributes can differ between items.

## Query vs Scan

```text
Query = targeted
Scan  = broad
```
