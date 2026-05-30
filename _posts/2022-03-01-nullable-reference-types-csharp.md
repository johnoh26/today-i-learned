---
title: "Nullable Reference Types in C# (.NET 6)"
date: 2022-03-01
categories:
  - tech
tags:
  - csharp
  - dotnet
  - security
excerpt: "Starting in .NET 6, enabling nullable context means reference types are no longer automatically nullable."
---

- Starting in .NET 6, with `<Nullable>enable</Nullable>` in the project file, reference types are no longer automatically nullable — you must explicitly opt in with `?`
- **Don't pass a DB entity object directly to logging** — it may contain sensitive data (EF proxies, navigation properties, etc.)

```csharp
// Instead of logging the full object:
_logger.LogInformation("{@entity}", dbEntity);

// Project only what you need:
var safeLog = thingToLog.Select(x => new { x.PropertyA, x.PropertyB });
_logger.LogInformation("{@data}", safeLog);
```
