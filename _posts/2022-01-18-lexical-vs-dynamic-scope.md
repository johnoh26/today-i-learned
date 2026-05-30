---
title: "Lexical vs. Dynamic Scope, and Pass by Value vs. Reference"
date: 2022-01-18
categories:
  - tech
tags:
  - cs-fundamentals
  - javascript
excerpt: "Lexical scope locks a variable to its definition site; dynamic scope follows the call stack."
---

## Lexical vs. Dynamic Scope

- **Lexical scope** — a variable's scope is defined at the point it is written; a function can only access variables in its own scope and parent scopes at definition time
- **Dynamic scope** — a function can access variables of any function currently on the call stack while it's running

Example: `main()` has a variable `scope`. Inside `main()` there's `firstFunc()`.
- **Lexical:** `firstFunc` cannot access `scope` unless it's passed in as an argument
- **Dynamic:** `firstFunc` can access `scope` because `main` is on the call stack

## Pass by Value vs. Pass by Reference

- **Pass by value** — a copy of the argument is made; changes inside the function don't affect the original
- **Pass by reference** — the function receives the actual reference; changes affect the original variable

Example: `mainVar = 5`, `firstFunc(arg)` sets `arg = 3` and returns it.
- Pass by value: `firstFunc(mainVar)` returns `3`, `mainVar` stays `5`
- Pass by reference: `firstFunc(mainVar)` returns `3`, `mainVar` becomes `3`
