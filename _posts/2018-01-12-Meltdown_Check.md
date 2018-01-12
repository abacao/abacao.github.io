---
layout: post
title: Quick Meltdown Check
---

Just run this simple command on the terminal:

```
dmesg | grep "Kernel/User page tables isolation: enabled" && echo "Cool! Patched! You are on the right way! :)" || echo "Shit, you are still vulnerable :("
```


AB
