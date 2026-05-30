---
title: "Type, Class, and Interface in TypeScript"
date: 2022-03-25
categories:
  - tech
tags:
  - typescript
  - javascript
excerpt: "TypeScript has a value space and a type space. Class lives in both; type and interface live only in the type space."
---

- TypeScript has a **value space** and a **type space**
- `class` exists in both spaces; `type` and `interface` exist only in the type space
- Use `type` when you don't need to specify method signatures; use `interface` when you do
- Use a function type to type a method
- Interfaces are easier to extend in TypeScript compared to classes, but it's largely a matter of preference
