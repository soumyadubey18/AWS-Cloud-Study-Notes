# 20 — DynamoDB

## What is DynamoDB?

DynamoDB is AWS's managed **NoSQL** database service.

**Memory:** DynamoDB = NoSQL.

## Basic structure

```text
Table
 └── Items
      └── Attributes
```

- **Table:** collection of items.
- **Item:** one record.
- **Attribute:** a piece of information belonging to an item.

## Partition Key

The partition key is the main key component used in DynamoDB's primary-key design and item distribution/access patterns.

**Memory:** Partition Key = Main key.

## Sort Key

The sort key is the second key component in a composite key. It works with the partition key to create unique combinations and supports ordered/range access among items sharing a partition-key value.

**Memory:** Sort Key = Second key.

## Composite Primary Key

**Composite key = Partition Key + Sort Key.**

The complete combination uniquely identifies an item.

**Memory:** Partition + Sort = Composite.

## Trainer hands-on table

| Setting | Value |
|---|---|
| Table | Students |
| Partition Key | RollNo |
| Key type | String |
| Sort Key | SchoolYear |
| Sort type | Number |
| Capacity mode | On-Demand |

Example:

```text
RollNo = 01, SchoolYear = 2026  → one unique item
RollNo = 01, SchoolYear = 2027  → different unique item
```

## On-Demand capacity

The trainer lab uses **On-Demand** capacity for the beginner exercise. The notes describe this as paying for requests rather than planning fixed capacity in advance and as convenient for development/testing/lab or unpredictable workloads.

## Query vs Scan

- **Query:** targeted lookup using a partition-key value and optional sort-key conditions.
- **Scan:** broader examination of table/index data to find matching items.

**Memory:** Query = targeted | Scan = inspect.

## Hands-on item examples

The lab creates:

### Item 1

```text
RollNo     = 01
SchoolYear = 2026
Name       = Bhupinder
```

### Item 2

```text
RollNo     = 02
SchoolYear = 2026
FavColor   = Red
```

The second item demonstrates the flexible/non-key attribute nature used in the trainer lab.
