---
title: "C# Basics: Projects, Assemblies, and XUnit"
date: 2022-02-02
categories:
  - tech
tags:
  - csharp
  - dotnet
  - testing
excerpt: "Project = .csproj file. Assembly = compiled .csproj. XUnit uses constructor/Dispose for setup/teardown."
---

- **Project** = a `.csproj` file
- **Assembly** = a `.csproj` compiled into a DLL or EXE
- Don't grant more access than necessary — using `public` for a property that doesn't need to be public is bad practice in principle; however, when testing API contracts, every property may need to be accessible
- **XUnit:**
  - Uses the class constructor for test initialization
  - Uses `Dispose` for test cleanup
  - Use `[Fact]` attribute for individual test cases
