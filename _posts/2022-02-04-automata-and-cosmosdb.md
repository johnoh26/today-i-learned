---
title: "Finite State Machines and CosmosDB Keys"
date: 2022-02-04
categories:
  - tech
tags:
  - cs-fundamentals
  - databases
  - azure
excerpt: "Automata = abstract machines. CosmosDB doesn't allow objects as keys — you must serialize them first."
---

- **Automata** means "abstract machine"
- A **Finite State Machine (FSM)** is a machine with a finite number of possible states — e.g., an espresso machine: On, Off, Brewing, Rest
- **CosmosDB:** document keys cannot be objects — you must serialize (stringify) the object before using it as a key
