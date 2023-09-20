---
layout: post
title:  "Glory of the Garden write-up"
date:   2023-09-18 16:21:22 -0400
categories: [picoCTF, picoCTF 2019]
---

After downloading the file named `garden.jpg`, all seemed usual, so let's try to open it with a hex editor and see what we can find.

Immediately, when opened with a hex editor and scroll to the bottom, we can see a hidden string. Which is our flag

![](https://i.imgur.com/iMkmVOs.png)

You can also simply do `strings garden.jpg | grep pico` and it will print out the flag for you.

Flag: `picoCTF{more_than_m33ts_the_3y3eBdBd2cc}`