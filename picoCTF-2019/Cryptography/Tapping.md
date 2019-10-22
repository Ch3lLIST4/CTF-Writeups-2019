# Tapping - Points: 200

## Problem

> Theres tapping coming in from the wires. What's it saying ```nc 2019shell1.picoctf.com 37920```.

## Hints

> What kind of encoding uses dashes and dots?

> The flag is in the format PICOCTF{}

## Overview

Let's trynna navigate to the server using netcat to port 37920 first.

```
$ nc 2019shell1.picoctf.com 37920

.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ...-- ----. -.... ----- ---.. ..... ....- ...-- ----. --... }

```

The server returned a string with dots and dashes. And looking at the format, I was pretty sure it's morse code.

## Solutions

I used this [online decoder](https://morsecode.scphillips.com/translator.html) for this. I excluded ```{``` and ```}``` just to make sure the code worked fine.

flag:
```
PICOCTF{M0RS3C0D31SFUN3960854397}
```
