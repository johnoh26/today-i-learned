---
title: "Domain Driven Design (DDD)"
date: 2022-03-09
categories:
  - tech
tags:
  - architecture
  - ddd
  - dotnet
excerpt: "Domain, subdomain, bounded context — the vocabulary of DDD."
---

- **Domain** — what the application is trying to achieve. For an accounting firm, the domain is accounting.
- **Subdomain** — a grouping of related business processes. Payroll, accounts payable, and accounts receivable would be subdomains of accounting. HR for an accounting firm would be an ancillary (supporting) domain.
- Similar business processes form a **problem space**
- A group of code for a subdomain is called a **bounded context** — these form the **solution space**

## ASP.NET Note

- `program.cs` is the entry point — run on application start, calls into `startup.cs`
- `startup.cs` is where you configure middleware, authentication, and other services
