---
layout: post
title: "1_wanna_b3_a_r0ck5tar write-up"
date: 2023-09-19 05:46:22 -0400
categories: [picoCTF, picoCTF 2019]
---

For this challenge, we are again given the source code for rockstar language, we need
to somehow make sense the the code as it does some if checks before printing the flag.

We really only need to translate the first few lines

```
# Rocknroll = true
Rocknroll is right
# Silence = false
Silence is wrong
# A guitar = 136
A guitar is a six-string
# Tommy = 44
Tommy's been down
# Music = 1970
Music is a billboard-burning razzmatazz!
# the music = input()
Listen to the music
# if (the music == 136)
If the music is a guitar
# print("Keep on rocking!")
Say "Keep on rocking!"
# the rhythm = input()
Listen to the rhythm
# if (the rhythm - Music === null)
If the rhythm without Music is nothing
```

We can see the first input check to see if `the music` is 136, and second checks to see if `the rhythm - Music` is null.

So our first input should be 136, and second should be 1970. Running this in the interpreter gives us the flag.

```
Keep on rocking!
66
79
78
74
79
86
73
```

Converting to ASCII string gives us `BONJOVI`

Flag: `picoCTF{BONJOVI}`
