---
layout: post
title:  "Warmed Up write-up"
date:   2023-09-18 16:24:22 -0400
categories: [picoCTF, picoCTF 2019]
---

The question asks us to convert `0x3D` to base 10, we can easily do this in Python

```python
int("0x3d", 16)
```

Which gives us `61`, so our flag is `picoCTF{61}`.