---
layout: post
title: "vault-door-5 write-up"
date: 2023-09-19 05:56:22 -0400
categories: [picoCTF, picoCTF 2019]
---

Opening the given `.java` file, we can see it is just checking for some encoded strings, we just have to reverse the logic

```java
public boolean checkPassword(String password) {
    String urlEncoded = urlEncode(password.getBytes());
    String base64Encoded = base64Encode(urlEncoded.getBytes());
    String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
                    + "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
                    + "JTM0JTVmJTY1JTMzJTMxJTM1JTMyJTYyJTY2JTM0";
    return base64Encoded.equals(expected);
}
```

To reverse using Node.js, we can just do

```js
const str =
  "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVmJTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2JTM0JTVmJTY1JTMzJTMxJTM1JTMyJTYyJTY2JTM0";
console.log(decodeURI(atob(str)));
```

And we get our flag: `picoCTF{c0nv3rt1ng_fr0m_ba5e_64_e3152bf4}`
