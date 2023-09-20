---
layout: post
title: "dont-use-client-side write-up"
date: 2023-09-19 05:32:22 -0400
categories: [picoCTF, picoCTF 2019]
---

We are presented with a login page, by viewing the page source, we can see the
actual JavaScript code used to validate the password.

```js
function verify() {
  checkpass = document.getElementById("pass").value;
  split = 4;
  if (checkpass.substring(0, split) == "pico") {
    if (checkpass.substring(split * 6, split * 7) == "723c") {
      if (checkpass.substring(split, split * 2) == "CTF{") {
        if (checkpass.substring(split * 4, split * 5) == "ts_p") {
          if (checkpass.substring(split * 3, split * 4) == "lien") {
            if (checkpass.substring(split * 5, split * 6) == "lz_7") {
              if (checkpass.substring(split * 2, split * 3) == "no_c") {
                if (checkpass.substring(split * 7, split * 8) == "e}") {
                  alert("Password Verified");
                }
              }
            }
          }
        }
      }
    }
  } else {
    alert("Incorrect password");
  }
}
```

Doing some quick reverse-engineering we get a more readable

```js
if (checkpass.substring(0, 4) == "pico") {
  if (checkpass.substring(24, 28) == "723c") {
    if (checkpass.substring(4, 8) == "CTF{") {
      if (checkpass.substring(16, 20) == "ts_p") {
        if (checkpass.substring(12, 16) == "lien") {
          if (checkpass.substring(20, 24) == "lz_7") {
            if (checkpass.substring(8, 12) == "no_c") {
              if (checkpass.substring(28, 32) == "e}") {
                alert("Password Verified");
              }
            }
          }
        }
      }
    }
  }
}
```

Now matching the substrings by index, we get the flag: `picoCTF{no_clients_plz_7723c}`
