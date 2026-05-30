---
title: "What Happens When You Type a URL Into a Browser"
date: 2022-01-03
categories:
  - tech
tags:
  - networking
  - web
  - dns
excerpt: "From URL parsing to page render — seven steps of what happens when you hit Enter."
---

1. `https://` is automatically added if missing; the URL is parsed to extract the domain name
2. The domain is resolved to an IP address via **DNS**
3. The browser sends a `GET` request to that IP address
4. The request is routed through various network devices: router, switch, load balancer, firewall
5. The request arrives at the server (e.g., Apache, NGINX); the server sends back a response
6. The browser receives the response and begins rendering, making additional requests as instructed
7. The browser renders what it has received while waiting for the rest
