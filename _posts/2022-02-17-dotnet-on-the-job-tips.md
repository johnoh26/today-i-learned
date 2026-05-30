---
title: "On-the-Job .NET Tips"
date: 2022-02-17
categories:
  - tech
tags:
  - dotnet
  - csharp
  - clean-code
excerpt: "Prefer broad types for interfaces. Make services internal unless they're meant for external use."
---

- **Prefer broad types for interfaces** — use `IEnumerable<T>` over `IList<T>` so the implementation can be a `List`, `Array`, or anything else without breaking the contract
- **Make services `internal` and interfaces `public`** unless a service is meant to be consumed outside the DLL — this exposes only the interface (not the specific implementation), eliminating confusion about what callers should depend on
