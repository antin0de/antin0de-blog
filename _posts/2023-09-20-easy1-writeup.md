---
layout: post
title: "Easy1 write-up"
date: 2023-09-20 07:56:22 -0400
categories: [picoCTF, picoCTF 2019]
---

For this challenge, we are given a table, a cryptotext, and a key, we need to solve
the OTP and decrypt the cryptotext.

The table is actually not needed, we could just simply write a Python script. I used a very
similar algorithm as described on the Wikipedia: https://en.wikipedia.org/wiki/One-time_pad

```python
text = 'UFJKXQZQUNB'
key = 'SOLVECRYPTO'

result = ""

for i in range(len(text)):
    c = text[i]
    k = key[i]
    ci = ord(c) - 65
    ki = ord(k) - 65
    plain = (ci - ki) % 26
    print(chr(plain + 65))
```

Running the script gives us the flag: `CRYPTOISFUN`

Flag: `picoCTF{CRYPTOISFUN}`
