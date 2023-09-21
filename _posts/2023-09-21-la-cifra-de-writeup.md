---
layout: post
title: "la cifra de write-up"
date: 2023-09-21 08:00:22 -0400
categories: [picoCTF, picoCTF 2019]
---

Initially I had no idea what this challange meant, a quick search reveals that apperantly
la cifra de has something to do with Vigenère cipher. So I used a tool online to try to do
some [frequency analysis](https://www.cryptool.org/en/cto/vigenerebreak).

After matching everything, we found the key to be `FLAGFLAG` (so really the key would be `FLAG`, but I chose length 8 as I thought
no way they gave us a length 4 key :).

![](https://i.imgur.com/bbm6mTJ.png)

The deciphered text contains the flag: `PICOCTF{B311A50_0R_V1GN3R3_C1PH3RA966878A}`
