---
title: "Reverse Proxy and Microservices"
date: 2022-03-14
categories:
  - tech
tags:
  - microservices
  - architecture
  - system-design
excerpt: "A microservice addresses one business problem. Calling services over the network without that discipline is just a distributed monolith."
---

## Microservice vs. Distributed Monolith

- A microservice should address one problem or a cohesive set of problems (business logic), with soft dependencies on other services (e.g., async via message queues)
- If you separate services but they call each other directly over the network for every operation, you have a **distributed monolith** — same coupling issues as a monolith, plus network overhead

## Reverse Proxy

- A reverse proxy can handle heavy shared operations like encryption/decryption that would otherwise be duplicated across many servers
- Can also be used as a load balancer
