---
layout: post
title:  "Let's Warm Up write-up"
date:   2023-09-18 16:20:22 -0400
categories: [picoCTF, picoCTF 2019]
---

The question here asks us what ASCII word starts with `0x70` in hex. We can do a quick conversion using Python

```python
chr(int("0x70", 16))
```

The result is `p`. Therefore our flag is `picoCTF{p}`