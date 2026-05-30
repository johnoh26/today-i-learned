---
title: "Async/Await Patterns in .NET"
date: 2022-02-18
categories:
  - tech
tags:
  - dotnet
  - csharp
  - async
excerpt: "Task.Run for async, Task.WhenAll for parallel, Parallel.ForEach for ordered parallel async."
---

```csharp
// Make a function async
Task.Run(() => SomeWork());

// Make parallel async calls and wait for all
await Task.WhenAll(task1, task2, task3);

// Run async calls in order and parallel (useful when progress tracking is needed)
await Task.Run(() => Parallel.ForEach(items, async item => await ProcessAsync(item)));
```
