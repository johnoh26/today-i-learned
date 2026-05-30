---
title: "JSON Web Tokens (JWT)"
date: 2022-02-16
categories:
  - tech
tags:
  - security
  - authentication
  - jwt
excerpt: "JWTs let a service trust a user without an extra DB call — but introduce their own tradeoffs."
---

- Storing session info in a DB increases latency (extra round-trip to validate the session)
- JWTs allow the service to trust the user without that DB call
- Tradeoffs: how do you expire or revoke a JWT?

## Symmetric vs. Asymmetric Keys

| | Symmetric | Asymmetric |
|---|---|---|
| Usage | Same key for encrypt and decrypt | One key encrypts, a different key decrypts |
| Risk | Losing the key means an attacker can forge tokens | A stolen public key can't forge tokens |
