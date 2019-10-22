# mus1c - Points: 300

## Problem
> I wrote you a [song](https://2019shell1.picoctf.com/static/200c6d216520c81a66af2c005736ae85/lyrics.txt). Put it in the picoCTF{} flag format

## Hints
> Do you think you can master rockstar?

## Overview

You may realize this immediately that they are using rockstar, an esoteric programming language in this text file. 


## Solutions

I was really lazy learning this programming language so i just used [this website](https://codewithrockstar.com/online) 

```
Output:
114
114
114
111
99
107
110
114
110
48
49
49
51
114
```

As you can see these are just some decimal numbers. Let's convert it to ASCII to see the result.

Result:
```
rrrocknrn0113r
```

flag:
```
picoCTF{rrrocknrn0113r}
```
