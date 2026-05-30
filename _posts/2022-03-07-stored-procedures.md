---
title: "Stored Procedures"
date: 2022-03-07
categories:
  - tech
tags:
  - databases
  - sql
  - security
excerpt: "Stored procedures are faster, support atomic transactions, and can be used for security — but business logic lives in the DB."
---

## Pros

- Faster execution (pre-compiled, cached execution plan)
- Can group multiple operations into an atomic transaction
- Security: create a role with access to specific stored procedures, preventing users from directly viewing or altering tables

## Cons

- Business logic leaks into the data access layer
- No version control (harder to track changes)
