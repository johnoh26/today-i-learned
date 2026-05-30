---
title: "I/O Devices and Peripherals"
date: 2022-01-01
categories:
  - tech
tags:
  - cs-fundamentals
  - systems
excerpt: "When you press a key, an interrupt fires, the CPU takes note, and it's stored in the keyboard buffer."
---

- When a key is pressed, an **interrupt** signals the CPU to take note and save the keystroke to the **keyboard buffer** — a queue similar to a printer queue
- This work is done by the **keyboard driver**; the interrupt mechanism and buffer are part of the OS
- Peripherals communicate with the computer via the physical layer (e.g., HDMI, USB, Bluetooth)
