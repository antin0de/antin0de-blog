---
layout: post
title: "First Grep write-up"
date: 2023-09-19 05:34:22 -0400
categories: [picoCTF, picoCTF 2019]
---

We are given a large text file, we can use `grep` to try to find substrings within
the large file.

```bash
cat file | grep picoCTF
```

This gives us the flag `picoCTF{grep_is_good_to_find_things_f77e0797}`
