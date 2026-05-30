---
title: "Load Balancers"
date: 2022-03-11
categories:
  - tech
tags:
  - system-design
  - networking
  - scalability
excerpt: "Load balancers distribute requests across servers using strategies like round robin, least load, or session affinity."
---

- Load balancers direct requests from clients to web servers or databases
- Common strategies: (weighted) round robin, random, least load, session/cookie affinity

## Layer 4 vs. Layer 7

| Type | Speed | Flexibility |
|------|-------|-------------|
| **Layer 4** | Faster | Lower — has access to header, IP, and port info only |
| **Layer 7** | Slower | Higher — can see payload, cookies, and full HTTP content |

Layer 4 is faster at the expense of flexibility. Layer 7 can make smarter routing decisions (e.g., route `/api` to one farm and `/static` to another).
