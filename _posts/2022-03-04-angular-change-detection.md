---
title: "Angular Change Detection"
date: 2022-03-04
categories:
  - tech
tags:
  - angular
  - javascript
excerpt: "Angular has two change detection strategies: Default and OnPush."
---

- Angular change detection triggers when there is an async operation
- Two change detection strategies:
  - **Default** — checks the entire component tree on any async event
  - **OnPush** — only updates the template if the component's input data has changed (more performant)

**Reference:** [The Last Guide for Angular Change Detection](https://mokkapps.de/blog/the-last-guide-for-angular-change-detection-you-will-ever-need/)
