---
title: "How DNS Works"
date: 2022-01-06
categories:
  - tech
tags:
  - networking
  - dns
  - protocols
excerpt: "Typing google.com kicks off a recursive DNS lookup through root servers, TLD servers, and domain name servers."
---

When you type a URL, the browser needs to resolve the domain name to an IP address. Here's how DNS handles it:

1. Request goes to one of the **13 root servers**
2. Root server directs to the **TLD name server** (e.g., `.com`, `.net`)
3. TLD name server points to the **domain name server** (e.g., `google.com`)
4. From there, it resolves the subdomain (e.g., `calendar.google.com`)

This process — from TLD down to subdomain — is called a **recursive lookup**.

It's expensive, so results are cached at multiple levels: ISP, root servers, domain servers.

Each TLD has one or more **registrars** that help people reserve names within that domain.
