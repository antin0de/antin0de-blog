---
layout: post
title: "Bases write-up"
date: 2023-09-19 05:33:22 -0400
categories: [picoCTF, picoCTF 2019]
---

We are asked to convert `bDNhcm5fdGgzX3IwcDM1` to the flag, which can easily
be done in Node.js

```js
atob("bDNhcm5fdGgzX3IwcDM1");
```

Which gives us the flag `l3arn_th3_r0p35`.

Flag: `picoCTF{l3arn_th3_r0p35}`
