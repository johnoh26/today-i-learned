---
title: "JavaScript: filter, map, reduce, and Type Coercion"
date: 2021-12-02
categories:
  - tech
tags:
  - javascript
  - cs-fundamentals
excerpt: "filter and map can mimic each other but produce different results. reduce is fundamentally different."
---

## filter vs. map vs. reduce

Given `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`, filtering for even numbers:

- `filter(x => x % 2 === 0)` → `[2, 4, 6, 8, 10]`
- `map(x => x % 2 === 0 ? x : undefined)` → `[undefined, 2, undefined, 4, ...]`

You can mimic `map` with `filter` and vice versa, but the results are different.

You **can't** replicate `reduce` with `filter`/`map` without an external variable — the function signatures are fundamentally different (`map`/`filter` return arrays; `reduce` returns a single value).

## JavaScript Type Coercion

- JavaScript has an interesting type coercion and conversion system
- **6 primitive types:** `number`, `boolean`, `null`, `undefined`, `string`, `symbol`
- **1 complex type:** `object`
- Values are **truthy** or **falsy** — truthy doesn't mean `=== true`, just that it coerces to true
- **Falsy values:** `""`, `''`, `0`, `-0`, `0n`, `null`, `undefined`, `NaN` — everything else is truthy
