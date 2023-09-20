---
layout: post
title: "reverse_cipher write-up"
date: 2023-09-19 06:30:22 -0400
categories: [picoCTF, picoCTF 2019]
---

For this challenge, we are given a text file and a binary file, opening the binary
file in Ghidra reveals a main function, after doing some renaming and cleaning up, we get the following C code:

```c
void main(void) {
  size_t read_flag_status;
  char flag_content [23];
  char eof;
  int read_flag_status_int;
  FILE *rev_this_file;
  FILE *flag_txt;
  uint j;
  int i;
  char c;

  flag_txt = fopen("flag.txt","r");
  rev_this_file = fopen("rev_this","a");
  if (flag_txt == (FILE *)0x0) {
    puts("No flag found, please make sure this is run on the server");
  }
  if (rev_this_file == (FILE *)0x0) {
    puts("please run this on the server");
  }
  read_flag_status = fread(flag_content,0x18,1,flag_txt);
  read_flag_status_int = (int)read_flag_status;
  if ((int)read_flag_status < 1) {
                    /* WARNING: Subroutine does not return */
    exit(0);
  }
  for (i = 0; i < 8; i = i + 1) {
    c = flag_content[i];
    fputc((int)c,rev_this_file);
  }
  for (j = 8; (int)j < 23; j = j + 1) {
    if ((j & 1) == 0) {
      c = flag_content[(int)j] + 5;
    }
    else {
      c = flag_content[(int)j] + -2;
    }
    fputc((int)c,rev_this_file);
  }
  c = eof;
  fputc((int)eof,rev_this_file);
  fclose(rev_this_file);
  fclose(flag_txt);
  return;
}
```

We can see it reads from flag.txt and does some scrambling and puts it into rev_this. On line 37 it skips first 8 chars since its `picoCTF{`

Then from line 41 to line 49, the logic is basically if index is even, add 5 to the ASCII code, otherwise -2. So we can write a simple Python script to do the reverse.

```python
s = "w1{1wq84fb<1>49"
r = ""
for i in range(0, len(s)):
    c = s[i]
    if i&1 == 0:
        r += chr(ord(c) - 5)
    else:
        r += chr(ord(c) + 2)
print(r)
```

Which gives us the flag `picoCTF{r3v3rs36ad73964}`
