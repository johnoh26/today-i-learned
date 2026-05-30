---
title: "Angular Forms, Arrow Functions, and LessCSS"
date: 2022-01-20
categories:
  - tech
tags:
  - angular
  - javascript
  - css
excerpt: "Template-driven vs reactive forms; function vs arrow function; LessCSS variables and nesting."
---

## Angular Forms

| Type | When to Use |
|------|-------------|
| **Template-driven** | Basic forms using `<form>` tag; bind `ngModel` to inputs; nest with `ngModelGroup` |
| **Reactive (programmatic)** | Complex forms; instantiate `FormGroup` and `FormControl` for granular validation |

## JavaScript: function vs. arrow function

- The `function` keyword creates its own execution context (affects `this`)
- Arrow functions do **not** create their own execution context — they inherit from the outer scope
- As a result, arrow functions **cannot** be used as constructors
- In a class: if you use `function` keyword for a method and call it in `setTimeout`, you may need to `.bind(this)` — arrow functions avoid this because they bind to the class scope

**Reference:** [Differences Between Arrow and Regular Functions](https://dmitripavlutin.com/differences-between-arrow-and-regular-functions/#1-this-value)

## LessCSS

- Declare variables and create functions/mixins to reduce style repetition
- Supports conditional operators
- Import variables and styles from other `.less` files
- Nest CSS rules like HTML — produces more readable stylesheets

**Reference:** [LessCSS Tutorial (YouTube)](https://www.youtube.com/watch?v=5mPEelNaZuc&list=PLLAZ4kZ9dFpNmzIb3XQi5QSFiEpK-UxUg)
