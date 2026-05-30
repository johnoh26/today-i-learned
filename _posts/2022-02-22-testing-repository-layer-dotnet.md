---
title: "Testing the Repository Layer in .NET"
date: 2022-02-22
categories:
  - tech
tags:
  - dotnet
  - csharp
  - testing
excerpt: "How to create an in-memory DB to test repository methods — EFFORT for SQL Server, Moq for CosmosDB."
---

- For **SQL Server + Entity Framework**, use [EFFORT](https://entityframeworkeffort.codeplex.com/) (Entity Framework Fake ObjectContext Realization Tool) to create an in-memory DB for testing repository methods
- For **CosmosDB**, you can use Moq directly: `Mock<ClassName>() { CallBase = true }` and set up methods from the parent class
  - Note: `Mock<ClassName>` is not the same as `Mock<InterfaceName>`
