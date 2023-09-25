---
layout: post
title: "Mr-Worldwide write-up"
date: 2023-09-24 08:00:22 -0400
categories: [picoCTF, picoCTF 2019]
---

This one is more like an amusing CTF rather than practical. So we get message
with pais of numbers seemingly to be coordinates. Plug these coordinates into
Google Maps reveals major cities.

```
Kyoto
Odessa
Dayton
Istanbul
Abu Dhabi
Kuala Lumpur
_
Addis Ababa
Loja
Amsterdam
Sleepy Hollow
Kodiak
Alexandria
```

Merging the first letters we get "Kodiak, Alaska", which is our answer

Flag: `picoCTF{KODIAK_ALASKA}`
