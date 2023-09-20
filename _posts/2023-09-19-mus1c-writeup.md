---
layout: post
title: "mus1c write-up"
date: 2023-09-19 05:41:22 -0400
categories: [picoCTF, picoCTF 2019]
---

For this challenge we are given a file with some song lyrics, this is a bit tricky
but it is basically a language called rockstar, you can run it online: https://codewithrockstar.com/

We get a list of numbers

```
114
114
114
111
99
107
110
114
110
48
49
49
51
114
```

Using a simple Python script, we can get the flag.

```py
s = """114
114
114
111
99
107
110
114
110
48
49
49
51
114"""

s = s.split('\n')
result = ""
for n in s:
    result += chr(int(n))
print(result)
```

Which is `picoCTF{rrrocknrn0113r}`
