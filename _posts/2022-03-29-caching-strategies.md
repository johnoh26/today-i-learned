---
title: "Caching Strategies"
date: 2022-03-29
categories:
  - tech
tags:
  - system-design
  - caching
  - databases
excerpt: "Five general caching strategies: cache-aside, write-through, write-back, read-through, and refresh-ahead."
---

Caching speeds up reads by storing data in RAM instead of hitting disk.

## The 5 Strategies

### Cache-Aside
Request data from cache first; if missing, go to DB and write it to cache.

- **Disadvantage:** cache miss results in 3 trips; data can become stale (use TTL to invalidate)

### Write-Through
Write to cache first, then to DB.

- **Disadvantage:** slower writes

### Write-Back
Write to cache; cache asynchronously writes to DB.

- **Disadvantage:** risk of data loss if cache goes down before writing

### Read-Through
Read from cache; if cache doesn't have the data, it fetches from DB.

- **Disadvantage:** data can become stale

### Refresh-Ahead
Cache anticipates which data to extend TTL on before expiry.

- **Disadvantage:** requires prediction logic
