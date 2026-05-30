---
title: "Scaling Databases: ACID and Replication"
date: 2022-03-15
categories:
  - tech
tags:
  - databases
  - scalability
  - sql
excerpt: "ACID guarantees and two replication strategies: master-slave and master-master."
---

## ACID Properties

| Property | Meaning |
|----------|---------|
| **Atomicity** | A transaction succeeds or fails as a whole |
| **Consistency** | Any transaction takes the DB from one valid state to another |
| **Isolation** | Concurrent transactions produce the same result as if run sequentially |
| **Durability** | Committed data persists, even through power loss |

## Replication

### Master-Slave
Read and write to master; master replicates to slaves. Slaves can replicate to other slaves (tree structure). Slaves offload reads.

- **Con:** Need logic to promote a slave to master if the master fails

### Master-Master
Two masters both support reads and writes. If one fails, the other takes over.

- **Cons:** Need to sync masters (may affect consistency); requires a load balancer

### General Con
If there are heavy writes, slaves will be busy relaying writes and can't help with reads.
