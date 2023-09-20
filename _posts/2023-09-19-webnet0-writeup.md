---
layout: post
title: "WebNet0 write-up"
date: 2023-09-19 07:56:22 -0400
categories: [picoCTF, picoCTF 2019]
---

For this challenge, we are given a TLS package capture file and a private key,
we can easily decrypt this with Wireshark.

Goto preferences, and we can add a new TLS key

![](https://i.imgur.com/736mRSx.png)

Then going back, we can follow the HTTP stream and find the flag in header

![](https://i.imgur.com/MsEENEs.png)

Flag: `picoCTF{nongshim.shrimp.crackers}`
