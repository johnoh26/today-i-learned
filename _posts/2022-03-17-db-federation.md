---
title: "Database Federation"
date: 2022-03-17
categories:
  - tech
tags:
  - databases
  - system-design
  - scalability
excerpt: "Federation (functional partitioning) splits data by function to reduce DB size and improve throughput."
---

Also called **functional partitioning** — split up data by function (e.g., users DB, products DB, orders DB).

## Pros

- Smaller individual databases → more data fits in memory → higher cache hit rate
- No single master DB handling all writes → reduces replication lag and improves throughput

## Cons

- Adds complexity when determining where to read from or write to
- Can constrain schema design
- Cross-domain joins require a server link
