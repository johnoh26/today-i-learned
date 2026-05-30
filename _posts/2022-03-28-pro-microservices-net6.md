---
title: "Pro Microservices with .NET 6"
date: 2022-03-28
categories:
  - tech
tags:
  - microservices
  - dotnet
  - architecture
  - ddd
excerpt: "In microservices, only interact with other aggregates through the aggregate root."
---

Notes from the Pro Microservices .NET 6 study club:

- In microservices, you shouldn't access the internals of another aggregate — only interact through the aggregate root
- DB schema changes shouldn't affect microservices as long as they can still get what they need; they don't have to use a new column that was added
- **Use a library when in the same subdomain; use an API when in a different domain** — if using a library and it gets updated, the consumer has to know about updates, whereas an API can just be updated on the server side (easier to manage)
