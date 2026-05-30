---
title: "Angular Modules, Routing, and Observables"
date: 2022-01-14
categories:
  - tech
tags:
  - angular
  - javascript
  - rxjs
excerpt: "A week of Angular: ngModule structure, routing with guards, and RxJS observables."
---

## Control Structures

`if` and `while` are examples of control structures. An `if` can serve as syntactic sugar for `switch`; a `while` can create a `for` loop.

## ngModule

Use modules to organize code. Each module has:

| Section | Purpose |
|---------|---------|
| `imports` | Use exported declarations from other modules |
| `exports` | Expose declarations for use by other modules |
| `declarations` | Directives, components, and pipes defined in this module |
| `providers` | Services available for dependency injection in this module |

## Angular Routing

- Use the app routing module to map paths to components
- `[routerLink]` paired with `<router-outlet>` controls where the routed component renders
- Guards control access to specific routes
- Inject `ActivatedRoute` to access query params

## Observables (RxJS)

- Observables are streams of events you subscribe to
- Three callbacks: `next`, `error`, `complete`
- **Always unsubscribe** to prevent memory leaks
- Use RxJS observables with Angular's `HttpClient` for the data layer
- Use `mergeMap` (instead of nested subscribes) to chain HTTP requests that depend on data from a previous observable
