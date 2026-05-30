---
title: "C# Protected Keyword and Angular Lifecycle Hooks"
date: 2022-03-03
categories:
  - tech
tags:
  - csharp
  - dotnet
  - angular
excerpt: "C# protected vs protected internal vs private protected — and Angular's lifecycle hook order."
---

## C# Access Modifiers

- `protected` — derived classes can access the member
- `protected internal` — accessible by derived classes **or** any code in the same assembly
- `private protected` — accessible only by derived classes **in the same assembly**
- `static` constructor — runs once, when the type is first used

## Angular Lifecycle Hooks (in order)

1. `ngOnChanges`
2. `ngOnInit`
3. `ngDoCheck`
4. `ngAfterContentInit`
5. `ngAfterContentChecked`
6. `ngAfterViewInit`
7. `ngAfterViewChecked`
8. `ngOnDestroy`
