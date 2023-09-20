---
layout: post
title: "picobrowser write-up"
date: 2023-09-19 05:35:22 -0400
categories: [picoCTF, picoCTF 2019]
---

This challenge tells us that the website can only be rendered using `picobrowser`. We know that when browser
sends HTTP requests, they usually send a header named `User-Agent` which tells the server what browser it is.

We can customize this header using `curl` command:

```bash
curl -A "picobrowser" https://jupiter.challenges.picoctf.org/problem/50522/flag | grep picoCTF
```

Above command gives us the following output:

```
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  2115  100  2115    0     0  13267      0 --:--:-- --:--:-- --:--:-- 13645
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_51414fa7}</code></p>
```

Which contains the flag: `picoCTF{p1c0_s3cr3t_ag3nt_51414fa7}`
