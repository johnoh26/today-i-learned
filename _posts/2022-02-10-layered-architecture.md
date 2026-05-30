---
title: "Layered Architecture"
date: 2022-02-10
categories:
  - tech
tags:
  - architecture
  - dotnet
  - clean-code
excerpt: "Always convert DB objects to DTOs, even if no modifications are needed — it prevents leaking sensitive data."
---

- **Always convert DB objects to DTOs** even if no modifications are needed — this prevents sensitive DB fields from leaking out of the service layer
- Conversion should happen in the service layer
- **Business Objects** combine various operations in one object
- **Services** focus on one thing and one thing only (Single Responsibility Principle) — a business object broken into focused classes
