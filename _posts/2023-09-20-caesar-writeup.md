---
layout: post
title: "caesar write-up"
date: 2023-09-20 07:58:22 -0400
categories: [picoCTF, picoCTF 2019]
---

Given the challenge name, the message is encrypted using caesar cipher, which can be solved
using brute-force. We use an online tool to do this https://cryptii.com/pipes/caesar-cipher

By trying different keys, shift 30 gives us the best result: `crossingtherubiconvfhsjkou`

So our flag is: `picoCTF{crossingtherubiconvfhsjkou}`
