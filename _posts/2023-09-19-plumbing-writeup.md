---
layout: post
title: "plumbing write-up"
date: 2023-09-19 05:37:22 -0400
categories: [picoCTF, picoCTF 2019]
---

For this challenge, after we connect with `nc`, we get a large blob of text. But we know that in bash
we can pipe the output of one command to another, so we can pipe the output of `nc` to `grep` to find
the flag.

```bash
nc jupiter.challenges.picoctf.org 14291 | grep picoCTF
```

We got our flag: `picoCTF{digital_plumb3r_ea8bfec7}`
