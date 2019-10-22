# 1_wanna_b3_a_r0ck5tar

## Problem
> I wrote you another [song](https://2019shell1.picoctf.com/static/ec882df63f9d0cfb8505879e0bc48c88/lyrics.txt). Put the flag in the picoCTF{} flag format

## Overview

Another rockstar challenge.


## Solutions

I didn't bother open up a file editor to analyze.

Instead I ran this command on my windows subsystem for extracting the text part that I needed.

```
$ strings garden.jpg | grep picoCTF
Here is a flag "picoCTF{more_than_m33ts_the_3y3cD8bA96C}"
```

So, the flag is:
```
picoCTF{more_than_m33ts_the_3y3cD8bA96C}
```
