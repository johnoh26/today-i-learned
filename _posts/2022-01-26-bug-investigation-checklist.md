---
title: "Bug Investigation Checklist"
date: 2022-01-26
categories:
  - tech
tags:
  - debugging
  - career
excerpt: "Encountered a 413 EntityTooLargeError. Checklist for investigating any production bug."
---

Encountered `413 EntityTooLargeError` in an API endpoint — caused by the cache exceeding its size limit.

## Bug Investigation Checklist

1. **Check the logging service first** — get the full set of errors and detailed logs
2. **Write reproduction steps**
3. **Run code locally** pointing at different environments — is it an env issue or a config issue?
4. **Redeploy / refresh deployment files** — see if that resolves it
5. **Try using a different slot** (e.g., Dev slot pointing at Staging) — rule out a slot issue
6. **At the end of the day**, it can only be one of: feature code, middleware, configuration, or storage
