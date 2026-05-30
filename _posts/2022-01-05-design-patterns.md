---
title: "Five Design Patterns"
date: 2022-01-05
categories:
  - tech
tags:
  - architecture
  - design-patterns
  - javascript
excerpt: "Null Object, Builder, Singleton, Facade, and Command patterns — with practical examples."
---

## Null Object

Instead of returning `null` and checking for it everywhere, create a `NullUser` class with safe default values.

```js
// Instead of: if (user.getName() !== null) { ... }
// Create NullUser that returns "Guest" — callers never need to null-check
```

## Builder

When a class has many optional properties, avoid ugly constructors with lots of `null` arguments:

```js
// Ugly: new User("Tom", null, null, "Sesame St")
// Better:
const user = new User("Tom");
user.setAge(21);
user.setAddress("Sesame St");
```

## Singleton

Use sparingly. Best for a single shared resource like an application-wide logger. Be cautious — singletons can make testing hard and changes have wide impact.

## Facade

Simplify and centralize complexity behind a clean interface. If you repeat the same verbose `fetch` setup everywhere, extract it into a `fetchApi(url, options)` wrapper.

## Command

Encapsulate operations as objects with `execute()` and `undo()` methods. A `Calculator` can maintain a `history` list of command objects and replay or undo them.

*This raised a question: does a Calculator class with all four math operations violate SRP? Or does the cohesion of "calculator behavior" justify it? It depends on whether you define the responsibility as "perform arithmetic" or "be a calculator."*
