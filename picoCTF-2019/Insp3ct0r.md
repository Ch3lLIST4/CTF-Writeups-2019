# The Factory's Secret

## Problem
>  Kishor Balan tipped us off that the following code may need inspection: https://2019shell1.picoctf.com/problem/63975/ ([link](https://2019shell1.picoctf.com/problem/63975/)) or http://2019shell1.picoctf.com:63975

## Hints

> How do you inspect web code on a browser?

> There's 3 parts

## Overview

Just a really basic web exploitation challenge using inspector for source code analyzing.

## Solutions

Go to the link and navigate to the inspector of your browser, Me simply presses Ctrl-U. 

There are 3 parts of the flag in every corner of the website including their css and js files. 


Combine them all together and you'll get the flag!

flag:
```
picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?d3db9182}
```
