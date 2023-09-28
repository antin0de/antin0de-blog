---
layout: post
title: "droids0 write-up"
date: 2023-09-27 08:03:22 -0400
categories: [picoCTF, picoCTF 2019]
---

For this challenge, we are given an APK file, we can use some standard tools
to analyze it, MobSF is a great tool, and if you don't mind the APK being shared
publicly, you can use the public demo instance.

After analyzing the APK, we found that it calls `Log` to log the flag

![](https://i.imgur.com/SKVmyG7.png)

This means we can use the `adb logcat` command to get the flag, simply installing
the APK in a virtual device, fire up `adb logcat` on your host machine, and click
the button. We get our flag.

Flag: `picoCTF{a.moose.once.bit.my.sister}`