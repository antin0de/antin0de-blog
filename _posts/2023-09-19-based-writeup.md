---
layout: post
title: "Based write-up"
date: 2023-09-19 05:36:22 -0400
categories: [picoCTF, picoCTF 2019]
---

For this challenge, after connecting with the server, we are prompted to convert
different numbers from different bases to ASCII.

Each conversion have a time limit, so I wrote a simple script that will convert
the numbers for you.

```python
s = input('first string: ')
s = s.split()
result = ''
for i in s:
    result += chr(int(i, 2))
print('result', result)

s = input('second string: ')
s = s.split()
result = ''
for i in s:
    result += chr(int(i, 8))
print('result', result)

s = input('third string: ')
s = [s[i:i + 2] for i in range(0, len(s), 2)]
result = ''
for i in s:
    result += chr(int(i, 16))
print('result', result)
```

Run above script and enter the numbers, and we got the flag: `picoCTF{learning_about_converting_values_02167de8}`
