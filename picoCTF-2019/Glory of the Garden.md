# Glory of the Garden

## Problem
> This [garden](https://2019shell1.picoctf.com/static/6b58b3859f377f1cf4cabb0188d35e5c/garden.jpg) contains more than it seems. You can also find the file in /problems/glory-of-the-garden_5_eeb712a9a3bc1998ffcd626af9d63f98 on the shell server.

## Hints
> What is a hex editor?

## Overview

As you can see, this challenge is related to the hex editor. They give you the file to analyze simply using a hex editor.


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
