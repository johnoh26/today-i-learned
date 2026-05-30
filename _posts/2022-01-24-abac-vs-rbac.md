---
title: "ABAC vs. RBAC"
date: 2022-01-24
categories:
  - tech
tags:
  - security
  - architecture
excerpt: "Attribute-Based Access Control scales better; Role-Based Access Control is simpler to set up."
---

## RBAC — Role-Based Access Control

Every user has a role; every role has access to certain areas. Common in small-to-medium enterprises. Variants: flat RBAC, hierarchical RBAC.

- **Pro:** Easier to set up
- **Con:** Can lead to "role explosion" as admins create more and more roles to achieve granular control at scale

## ABAC — Attribute-Based Access Control

Access is controlled by policies that check for specific attributes. More setup upfront, but scales much better.

- **Pro:** Easier to scale; fine-grained control
- **Con:** Higher setup effort
