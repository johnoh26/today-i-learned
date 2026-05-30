---
title: "How the Internet Works: TCP, DNS, and Packets"
date: 2022-01-07
categories:
  - tech
tags:
  - networking
  - protocols
  - tcp
  - dns
excerpt: "After DNS resolves the IP, a 3-way handshake establishes TCP. IP breaks requests into packets that can arrive out of order."
---

- After a URL is entered and the IP resolved via DNS, the **3-way handshake** happens:
  1. Client sends `SYN`
  2. Server responds `SYN-ACK`
  3. Client sends `ACK`
- The 3-way handshake establishes the TCP connection
- UDP is connectionless — no handshake, less reliable, but faster
- IP breaks requests into **packets** that are sent independently; they can arrive out of order or not at all
- TCP uses a **checksum** to verify all sent packets have arrived
  - If checksum fails, the packet is discarded
  - Small chance checksum passes despite corruption
- To see how many hops a request takes: `traceroute google.com` (macOS/Linux)
- Make requests faster by using a CDN or reducing packet count
