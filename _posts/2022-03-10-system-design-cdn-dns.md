---
title: "System Design: CDN and DNS"
date: 2022-03-10
categories:
  - tech
tags:
  - system-design
  - networking
  - cdn
  - dns
excerpt: "Maximize throughput given acceptable latency. CDNs and DNS are key tools in that effort."
---

- Core goal: maximize throughput given acceptable latency

## Content Delivery Network (CDN)

CDNs deliver content more quickly by being globally distributed closer to users.

- **Push CDN** — you push content to the CDN; more flexibility (push timing, expiration, what to push)
- **Pull CDN** — CDN pulls content from you on demand; easier to set up but can cause slow initial UX until content is pulled, and some redundant traffic from re-queries

## DNS (Domain Name System)

- DNS translates website names to IP addresses so people don't have to remember them
- Usually provided by ISPs, governments, or tech companies
- If DNS is attacked or goes down, the web becomes hard to navigate
