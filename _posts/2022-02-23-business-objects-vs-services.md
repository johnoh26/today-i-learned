---
title: "Business Objects vs. Services"
date: 2022-02-23
categories:
  - tech
tags:
  - architecture
  - dotnet
  - clean-code
excerpt: "Repository → Business Object → Service: each layer adds abstraction and responsibility."
---

- **Repository layer** — accesses the database. Methods should be simple LINQ-style queries with minimal logic
- **Business Object (BO)** — contains logic in addition to the repository layer. Allows the repo layer to change without affecting the BO
- **Service** — a BO broken into individual method-focused classes (e.g., `ClassUpdateService`, `ClassCreationService`, `ClassDeletionService`) following the Single Responsibility Principle
