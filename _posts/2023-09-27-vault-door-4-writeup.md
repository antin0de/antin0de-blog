---
layout: post
title: "vault-door-4 write-up"
date: 2023-09-27 08:02:22 -0400
categories: [picoCTF, picoCTF 2019]
---

The challenge for this question is just to convert number in different bases
to ASCII. First two rows are obvious, the third row is octal, which is representted
in Python with `0o` prefix. We can just manually convert all of them.

```python
"""
106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
0142, 0131, 0164, 063 , 0163, 0137, 070 , 0146,
'4' , 'a' , '6' , 'c' , 'b' , 'f' , '3' , 'b' ,
"""

suffix = '4a6cbf3b'
result = ''
numbers = [
    106,
    85,
    53,
    116,
    95,
    52,
    95,
    98,
    0x55,
    0x6e,
    0x43,
    0x68,
    0x5f,
    0x30,
    0x66,
    0x5f,
    0o142,
    0o131,
    0o164,
    0o63,
    0o163,
    0o137,
    0o70,
    0o146,
]

for n in numbers:
  result += chr(n)
result += suffix
print(result)
```

Running above script yields the flag: `jU5t_4_bUnCh_0f_bYt3s_8f4a6cbf3b`