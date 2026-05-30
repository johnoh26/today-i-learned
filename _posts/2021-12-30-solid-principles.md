---
title: "SOLID Principles"
date: 2021-12-30
categories:
  - tech
tags:
  - architecture
  - clean-code
  - design-patterns
excerpt: "Five principles for writing maintainable, extensible object-oriented code."
---

*Source: Web Dev Simplified and Tim Corey on YouTube*

## 1. Single Responsibility

A class should have only one reason to change.

**Bad:** `CalorieTracker` has both `calculateCalories()` and `logCalories()`
**Fix:** Extract a `Logger` class; remove `logCalories` from `CalorieTracker`

## 2. Open/Closed

Open for extension, closed for modification.

**Bad:** A `Problem` class with a `switch` statement for each question type — adding a new type requires modifying existing code
**Fix:** Create a class for each question type with a shared interface (e.g., `displayQuestion()`). Adding new types requires no changes to existing code.

## 3. Liskov Substitution

A subclass should be substitutable for its parent class.

**Bad:** `Square` inherits from `Rectangle`; increasing width by 1 changes the area differently for each (a square's height increases too)
**Fix:** Create a `Shape` parent class that both `Square` and `Rectangle` inherit from

**Bad:** `Bird` with `fly()` and `swim()` — `Penguin` can't fly
**Fix:** Create `FlyingBird`, `SwimmingBird`, etc. Prefer composition over inheritance in JavaScript.

## 4. Interface Segregation

Don't force classes to implement methods they don't need.

**Bad:** `IBird` interface with both `fly()` and `swim()` — `Penguin` would have to implement `fly()`
**Fix:** Break into `IFlyingBird` and `ISwimmingBird`. You can combine interfaces: `IBorrowableBook : IBook, IBorrowable`

## 5. Dependency Inversion

Depend on abstractions, not concretions.

**Bad:** Code depends directly on Stripe API or PayPal API
**Fix:** Wrap them in a `PaymentProcessor` interface — existing code depends on the abstraction, not the specific vendor
