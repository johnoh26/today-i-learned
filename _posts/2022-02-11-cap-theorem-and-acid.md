---
title: "CAP Theorem and ACID Properties"
date: 2022-02-11
categories:
  - tech
tags:
  - databases
  - distributed-systems
  - system-design
excerpt: "CAP theorem: you can only have two of Consistency, Availability, and Partition Tolerance."
---

*Source: Hussein Nasser's YouTube channel*

## CAP Theorem

A distributed system can only guarantee **two** of:

- **Consistency** — every read gets the most recent write
- **Availability** — every request gets a response
- **Partition Tolerance** — the system continues operating despite network partitions between nodes

## ACID Properties (detailed)

### Atomicity
A transaction (which may involve multiple operations) either fully succeeds or fully fails — never partially.

### Consistency
Data is consistent across the DB. Example: the like count in the `POSTS` table should always equal the number of rows in the `LIKES` table for that post.

### Isolation
Multiple isolation levels exist:

| Level | Behavior |
|-------|----------|
| Read Uncommitted | Returns all data, even mid-transaction |
| Read Committed | Returns only committed data |
| Repeatable Read | Versions the DB — repeated reads return the same result |
| Lock | Exclusive lock for writes; shared lock for reads |

### Durability
Once committed (and the DB confirms it), data must persist even through a power loss. A cache is an example of a non-durable store.
