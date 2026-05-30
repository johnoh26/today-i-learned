---
title: "Microservices Overview"
date: 2022-02-28
categories:
  - tech
tags:
  - microservices
  - architecture
  - scalability
excerpt: "Monoliths are fine until scale demands otherwise. Microservices add complexity but enable horizontal scaling."
---

- Monoliths are fine but hit limits at scale
- Microservices scale well horizontally but add complexity
- Each server should be **stateless** — a user's request could be served by any server in the pool
- Deploying all servers at once can be done via tools like Capistrano (for Rails)
- **Don't have services call other services** — if there is shared/core code, use a library (it gets included in the same process)
- Separate deployability and fault isolation are key benefits of microservices over monoliths
- Distributed monoliths are undesirable but can be a pragmatic stepping stone toward true microservices
