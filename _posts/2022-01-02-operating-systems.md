---
title: "Operating Systems"
date: 2022-01-02
categories:
  - tech
tags:
  - cs-fundamentals
  - systems
excerpt: "An OS glues together peripherals, networking, memory, storage, and processing. It's split into kernel space and user space."
---

- An OS glues together the pillars of a computer: peripherals, networking, memory, storage, and processing
- Examples: iOS, Windows, macOS, Linux, Unix. Server OSes: IOS (Cisco), Junos (Juniper)
- OSes used to be stored in ROM; as they grew larger, a **boot loader** was needed to load the rest of the OS from disk (called **booting**)
- **BIOS** (Basic I/O System) — stored in flash memory, handles early I/O before the OS is loaded
- An OS has two main parts: the **kernel** and everything else
  - **Kernel space** — only code executing inside the kernel can access it
  - **User space** — accessible by end-user programs running on top of the OS
