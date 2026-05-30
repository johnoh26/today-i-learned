---
title: "Mocking Lambda Expressions in C#"
date: 2022-02-15
categories:
  - tech
tags:
  - csharp
  - dotnet
  - testing
excerpt: "You can't mock a lambda expression directly in Moq — you need to match the Expression type."
---

Mocking a method that takes a lambda like `method(x => x.Version == someValue)` does **not** work with a naive `It.IsAny<string>()` matcher.

You need to match the `Expression` type:

```csharp
mock.Setup(m => m.Method(It.IsAny<Expression<Func<OutputName, bool>>>()))
    .Returns(...);
```

To test what's *inside* the lambda expression, add a `.Callback()` to capture and inspect the argument — the mock gets more involved but is doable.
