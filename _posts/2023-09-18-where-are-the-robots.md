---
layout: post
title:  "where are the robots write-up"
date:   2023-09-18 16:26:22 -0400
categories: [picoCTF, picoCTF 2019]
---

When visiting the website, we are initially presented with a screen along a simple message

![](https://i.imgur.com/5yZhZup.png)

And we know for websites, there is a special file called `robots.txt` that controls how web spiders indexes your site, so let's try accessing that file.

The result came back with a single `Disallow` rule.

```
User-agent: *
Disallow: /8028f.html
```

Let's visit the file indicated by the rule, and we get our flag

![](https://i.imgur.com/Hp2s34R.png)

Flag: `picoCTF{ca1cu1at1ng_Mach1n3s_8028f}`