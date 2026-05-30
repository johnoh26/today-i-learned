---
title: "Address Resolution Protocol (ARP)"
date: 2022-02-08
categories:
  - tech
tags:
  - networking
  - protocols
excerpt: "ARP maps IP addresses to MAC addresses at Layer 2."
---

- ARP is a mapping between IP address and MAC (Media Access Control) address
- We have the destination IP address, but we need the MAC address to operate at Layer 2
  - Layer 2: MAC address
  - Layer 3: IP address
  - Layer 7: HTTP request
- Flow: send an ARP request to the IP address → receive the MAC address → store it in the local ARP table
- **Security note:** man-in-the-middle attacks and ARP poisoning/corruption attacks exist
