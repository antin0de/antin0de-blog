---
layout: post
title: "WhitePages write-up"
date: 2023-09-25 09:00:22 -0400
categories: [picoCTF, picoCTF 2019]
---

After opening this file and reading with Python, we can see the file contains
two types of spaces, one is `\u2003`, another one is regular space. We can try
to convert these different spaces into binary format

```python
r = ""
with open("whitepages.txt", "r") as file:
    content = file.readlines()
    content = "".join(content)
    for c in content:
        if c == "\u2003":
            r += "0"
        else:
            r += "1"
print(r)
```

Pasting the output binary into a converter like https://onlinebinarytools.com/convert-binary-to-ascii will give us the flag

Flag: `picoCTF{not_all_spaces_are_created_equal_3e2423081df9adab2a9d96afda4cfad6}`
