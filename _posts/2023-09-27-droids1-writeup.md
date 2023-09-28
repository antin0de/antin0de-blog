---
layout: post
title: "droids1 write-up"
date: 2023-09-27 08:07:22 -0400
categories: [picoCTF, picoCTF 2019]
---

Same as droids0, in this case let's actually try install this apk first. We see that
there is a password input box, and we just need to crack the password.

So again, using MobSF, we see the source code

![](https://i.imgur.com/0CbXATf.png)

We can see there is a resource string called "password", simply go to the "Hardcoded Secrets" part of MobSF, we see the password

![](https://i.imgur.com/IxpSsGQ.png)

Typing this password, we get our flag: `picoCTF{pining.for.the.fjords}`