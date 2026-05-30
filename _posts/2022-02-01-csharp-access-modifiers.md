---
title: "C# Access Modifiers and Keywords"
date: 2022-02-01
categories:
  - tech
tags:
  - csharp
  - dotnet
excerpt: "Abstract, virtual, interface, sealed, protected, readonly, and const — a quick reference."
---

## Classes and Inheritance

| Keyword | Meaning |
|---------|---------|
| `abstract class` | Contains one or more abstract methods |
| `abstract method` | No implementation — must be overridden by derived classes |
| `virtual method` | Has a default implementation — can be overridden |
| `interface` | Only method signatures, no implementations |
| `sealed` | Prevents further inheritance |
| `protected` | Like `private`, but accessible by derived classes |

## Constants

| Keyword | Evaluated |
|---------|-----------|
| `readonly` | Runtime constant |
| `const` | Compile-time constant |
