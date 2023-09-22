---
layout: post
title: "vault-door-3 write-up"
date: 2023-09-22 08:02:22 -0400
categories: [picoCTF, picoCTF 2019]
---

For this challenge, we are asked to revert the following algorithm

```java
public boolean checkPassword(String password) {
    if (password.length() != 32) {
        return false;
    }
    char[] buffer = new char[32];
    int i;
    for (i=0; i<8; i++) {
        buffer[i] = password.charAt(i);
    }
    for (; i<16; i++) {
        buffer[i] = password.charAt(23-i);
    }
    for (; i<32; i+=2) {
        buffer[i] = password.charAt(46-i);
    }
    for (i=31; i>=17; i-=2) {
        buffer[i] = password.charAt(i);
    }
    String s = new String(buffer);
    return s.equals("jU5t_a_sna_3lpm18g947_u_4_m9r54f");
}
```

Initially I was trying to do it by hand, but it is way too confusing, so instead
I tried to use JS to reconstruct an index mapping. I used JavaScript because the
original language is Java, it is just easier compared to Python.

```js
let mapping = {}

let i;
for (i = 0; i < 8; i++) {
    mapping[i] = i;
}
for (; i < 16; i++) {
    mapping[23 - i] = i;
}
for (; i < 32; i += 2) {
    mapping[46 - i] = i;
}
for (i = 31; i >= 17; i -= 2) {
    mapping[i] = i;
}

const check = "jU5t_a_sna_3lpm18g947_u_4_m9r54f"
let result = ""
for (i = 0; i < 32; i++) {
    result += check.charAt(mapping[i])
}

console.log(result)
```

The flag is: `picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_79958f}`