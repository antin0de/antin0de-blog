---
layout: post
title: "The Numbers write-up"
date: 2023-09-19 08:58:22 -0400
categories: [picoCTF, picoCTF 2019]
---

Opening this picture reveals a list of numbers, I immediately tried to decode using ASCII, but failed.

After looking more closely, I find that it is too low to be ASCII, so perhaps there is an offset. I know the first character must be `p`, so computing the offset is easy.

```python
offset = ord('p') - 16
# 96
```

Then we can compute the flag

```python
nums = [16, 9, 3, 15, 3, 20, 6, 20, 8, 5, 14, 21, 13, 2, 5, 18, 19, 13, 1, 19, 15, 14]

r = ""
for n in nums:
    r += chr(n + 96)
print(r)
```

This gives us `picoctfthenumbersmason`;

Flag: `picoCTF{thenumbersmason}`
