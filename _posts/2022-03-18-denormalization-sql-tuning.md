---
title: "Denormalization and SQL Tuning"
date: 2022-03-18
categories:
  - tech
tags:
  - databases
  - sql
  - performance
excerpt: "Denormalization creates duplicate data to avoid expensive joins, especially in sharded databases."
---

## Denormalization

- Create duplicate data/writes to avoid expensive joins, especially when the DB is sharded or using federation
- **Cons:** writes take longer; adds complexity

## SQL Tuning

Two approaches to finding performance issues:

- **Benchmarking** — simulate high-load situations
- **Profiling** — track performance issues (e.g., using the slow query log)
