---
layout: post
title:  "Big Zip write-up"
date:   2023-09-18 15:17:22 -0400
categories: [picoCTF, picoGym Exclusives]
---

Unzipping `big-zip-files.zip` gives us quite a lot of files to go through. It is not really feasible to manually go through
every single file.

Fortunately, grep is able to recursively find strings within a directory.

```
-R, -r, --recursive
    Recursively search subdirectories listed.  (i.e., force grep to behave as rgrep).
```

So we can `cd` into the directory and try to grep `pico`

```
➜  big-zip-files grep -r pico .
./folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
```

And we got our flag: `picoCTF{gr3p_15_m4g1c_ef8790dc}`