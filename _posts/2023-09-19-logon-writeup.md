---
layout: post
title: "logon write-up"
date: 2023-09-19 05:31:22 -0400
categories: [picoCTF, picoCTF 2019]
---

After visiting the website, we are given a login page, trying `admin` as username and `admin` as password, we are able to login, but can't get the flag.

![](https://i.imgur.com/s4HZyOi.png)

Poking around the cookies, we found a cookie called `admin`, which is set to `False`, let's flip it to `True`.

![](https://i.imgur.com/Q1k0zzd.png)

Reloading the page reveals the flag.

![](https://i.imgur.com/kEbTmX6.png)

Flag: `picoCTF{th3_c0nsp1r4cy_l1v3s_6edb3f5f}`
