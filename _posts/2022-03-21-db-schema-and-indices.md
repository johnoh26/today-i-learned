---
title: "Tightening DB Schema and Using Better Indices"
date: 2022-03-21
categories:
  - tech
tags:
  - databases
  - sql
  - performance
excerpt: "Good indices and a tight schema can significantly improve query performance."
---

- `SELECT`, `JOIN`, `ORDER BY`, and `GROUP BY` operations can all benefit from well-chosen indices
- DB indices use a B-tree structure — a balanced tree is a generalized form of BST that can have many branches
- Tighten schema by using `CHAR` instead of `VARCHAR` where appropriate, and using `NOT NULL` constraints
