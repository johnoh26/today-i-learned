---
title: ".NET Async/Await Deep Dive"
date: 2022-01-28
categories:
  - tech
tags:
  - dotnet
  - csharp
  - async
excerpt: "The async keyword creates a state machine under the hood. await creates checkpoints that machine can jump to."
---

- The `async` keyword creates a **state machine** under the hood — visible by inspecting the IL using ILSpy
- The `await` keyword creates checkpoints the state machine can jump to
- Using an `async` function propagates upward — if you `await` inside `Main()`, then `Main()` must also be `async`

**Reference:** [Raw Coding — Async Deep Dive (YouTube)](https://youtube.com/watch?v=il9gl8MH17s)
