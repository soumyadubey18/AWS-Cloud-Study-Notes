# 02 — AWS Global Infrastructure

## Region

A **Region** is a geographical AWS location.

**Remember:** Region = big geographic location.

## Availability Zone (AZ)

An **Availability Zone** is an isolated infrastructure location inside a Region. A Region contains multiple AZs.

**Remember:** Region → multiple AZs.

## Edge Location

The revision material describes an **Edge Location** as a location used for CloudFront caching.

## Local Zone

The revision material describes a **Local Zone** as a location used to provide lower-latency infrastructure closer to a city or metro area.

## Simple memory

```text
Region
  ├── AZ-1
  ├── AZ-2
  └── AZ-3
```

## Why multiple AZs?

Using multiple AZs supports availability and fault tolerance by spreading resources across isolated locations.
