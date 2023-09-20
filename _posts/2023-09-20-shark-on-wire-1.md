---
layout: post
title: "shark on wire 1 write-up"
date: 2023-09-20 07:59:22 -0400
categories: [picoCTF, picoCTF 2019]
---

After opening the capture file within Wireshark, there isn't any obvious streams we can follow. But seems like
there are quite a few UDP streams we can look into.

In Wireshark, we can filter streams based on index by using the filter `udp.stream eq INDEX`

After trying a few, `udp.stream eq 6` yielded the right flag

![](https://i.imgur.com/bW3VaDY.png)

Our flag is: `picoCTF{StaT31355_636f6e6e}`
