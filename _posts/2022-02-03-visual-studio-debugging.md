---
title: "Visual Studio Debugging Tips"
date: 2022-02-03
categories:
  - tech
tags:
  - dotnet
  - debugging
  - visual-studio
excerpt: "Can't set a breakpoint? Check which folders VS is looking in for the DLL and copy the DLL + PDB there."
---

**When you can't set a breakpoint:**

1. Start debugging
2. Go to **Debug → Windows → Modules**
3. Find the DLL in use
4. Check which folders VS looked in to locate the DLL
5. Copy the DLL and its `.pdb` file into that folder

**Design question worth exploring:** Is unit testing necessary for a repository layer that has no business logic? If so, how do you correctly test it?
