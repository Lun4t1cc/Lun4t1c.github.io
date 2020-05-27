---
title: 在 libc 文件中寻找 gadgets
category: 代码片段
layout: post
---

```python
pop_rdi_ret = libc_base + libc.search(asm("pop rdi\nret")).next()
pop_rsi_ret = libc_base + libc.search(asm("pop rsi\nret")).next()
pop_rdx_ret = libc_base + libc.search(asm("pop rdx\nret")).next()
```