---
title: "ASP.NET and the MVC Pattern"
date: 2022-03-08
categories:
  - tech
tags:
  - dotnet
  - architecture
  - aspnet
excerpt: "MVC has a long history. ASP.NET added routing as a fourth element."
---

Notes from Chapter 2 of *Pro Microservices with .NET 6*:

- MVC has a long history — ASP.NET incorporated it since WinForms
- **Routing** was added as a fourth element in ASP.NET

## MVC Roles

| Component | Responsibility |
|-----------|---------------|
| **Controller** | Routes requests to the right model; can contain validation and logging |
| **Model** | Business logic |
| **View** | Binds data to HTML |

- A web framework essentially deals with the request-to-response pipeline
