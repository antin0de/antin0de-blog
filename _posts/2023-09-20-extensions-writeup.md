---
layout: post
title: "extensions write-up"
date: 2023-09-20 08:00:22 -0400
categories: [picoCTF, picoCTF 2019]
---

The text file can be opened within an editor like JetBrains Fleet, after opening, we see that it is actually
a PNG image, so we can change the extension.

All we have to do is `mv flag.txt flag.png` and open it.

> note: we can also do `file flag.txt` to verify the file format, in this case, it will confirm it is a PNG file

![](https://i.imgur.com/hFl89ye.png)

The flag is: `now_you_know_about_extensions`
