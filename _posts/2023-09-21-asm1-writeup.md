---
layout: post
title: "asm1 write-up"
date: 2023-09-21 08:02:22 -0400
categories: [picoCTF, picoCTF 2019]
---

For this challenge, we need to understand the given assembly file, we could just
use ChatGPT or some other tools to help us understand it, I used [this tool](https://www.codeconvert.ai/assembly-to-c-converter).

The converted C code is a bit incorrect, but we can see that it is either adding 10 or subtracting 10 from the argument

```c
int asm1(int arg) {
    if (arg > 0x3fb) {
        if (arg == 0x280) {
            return arg + 0xa;
        } else {
            return arg - 0xa;
        }
    } else {
        if (arg == 0x559) {
            return arg - 0xa;
        } else {
            return arg + 0xa;
        }
    }
}
```

so we can just try both, and the flag turns out to be `2d6`
