---
title: "BASE Properties of NoSQL Databases"
date: 2022-03-24
categories:
  - tech
tags:
  - databases
  - nosql
excerpt: "Like ACID for SQL databases, NoSQL databases follow BASE: Basically Available, Soft state, Eventual consistency."
---

There are various types of NoSQL databases: key-value stores, document stores, graph stores, etc.

Like ACID for SQL databases, NoSQL databases follow **BASE**:

| Property | Meaning |
|----------|---------|
| **B**asic **A**vailability | The system prioritizes availability |
| **S**oft State | Data can change without an input due to eventual consistency |
| **E**ventual Consistency | Data will eventually become consistent across nodes |
