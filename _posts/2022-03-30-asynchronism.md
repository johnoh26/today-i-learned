---
title: "Asynchronism with Message Queues"
date: 2022-03-30
categories:
  - tech
tags:
  - system-design
  - architecture
  - message-queues
excerpt: "Task and message queues decouple work that doesn't need to be synchronous."
---

- Task/message queues can achieve asynchronism
- Helps with request latency when an operation doesn't need to be synchronous — e.g., posting a tweet and notifying followers can be decoupled; it's fine for notifications to arrive with a slight delay
- Flow: add a message/task to the queue → message brokers check the queue and notify relevant worker processes → workers execute and signal completion
