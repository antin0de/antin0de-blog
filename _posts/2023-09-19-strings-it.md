---
layout: post
title: "strings it write-up"
date: 2023-09-19 05:30:22 -0400
categories: [picoCTF, picoCTF 2019]
---

For this challenge we are given a binary file, all we need to do is use the
`strings` command to extract strings from the given binary.

```bash
strings strings | grep picoCTF
```

And we got our flag: `picoCTF{5tRIng5_1T_d66c7bb7}`
