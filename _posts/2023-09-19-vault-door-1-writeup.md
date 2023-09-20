---
layout: post
title: "vault-door-1 write-up"
date: 2023-09-19 08:59:22 -0400
categories: [picoCTF, picoCTF 2019]
---

The `.java` file seems to be checking password character by character, so really
all we need to do is to re-construct the full string. Of course programmers are lazy so I wrote a script to do it for you

```python
s = """
               password.charAt(0)  == 'd' &&
               password.charAt(29) == '9' &&
               password.charAt(4)  == 'r' &&
               password.charAt(2)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(3)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(1)  == '3' &&
               password.charAt(7)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(5)  == '4' &&
               password.charAt(9)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(8)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(6)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == '5' &&
               password.charAt(30) == '2' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == '0' &&
               password.charAt(26) == '7' &&
               password.charAt(31) == 'e';
"""

result = [' '] * 32
for line in s.split('\n'):
    line = line.strip()
    if line:
        index = int(line.split('(')[1].split(')')[0])
        c = line.split("'")[1].split("'")[0]
        result[index] = c
print("".join(result))
```

Running the script gives us the flag `picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_75092e}`
