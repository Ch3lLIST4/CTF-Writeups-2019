# Mr-Worldwide - Points: 200

## Problem

> A musician left us a [message](https://2019shell1.picoctf.com/static/46e165b0a953075440f3a544fdb4cff1/message.txt). What's it mean?

## Overview

I was really confused about the keyword **musician** for the problem. Then I realized it has nothing to do with this challenge.   

Opening the given file. We got
```
picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)}
```
It looks like it really is the flag and it's in the right format already. I guessed there were 2 parts and 6 characters for each part.

The real problem are those numbers. What's that kind of cipher anyways ?

## Solutions

These pairs of numbers are like coordinates and that's the first thing I think of when I look at these numbers, especially when the title is ```Worldwide```. Let's try using some tools online to investigate these locations. I simply just used Google Map.

Then I tried concatenate all of the locations using their country names. I even investigate all of the pictures that related to the locations and so on, but I failed.. then I kept trying and trying until I found this. 

```
[K]yoto             (35.028309, 135.753082)
[O]dessa            (46.469391, 30.740883)
[D]ayton            (39.758949, -84.191605)
[I]stanbul          (41.015137, 28.979530)
[A]bu Dhabi         (24.466667, 54.366669)
[K]uala Lumpur      (3.140853, 101.693207)
_
[A]ddis Ababa       (9.005401, 38.763611)
[L]oja              (-3.989038, -79.203560)
[A]msterdam         (52.377956, 4.897070)
[S]leepy Hollow     (41.085651, -73.858467)
[K]odiak            (57.790001, -152.407227)
[A]lexandria        (31.205753, 29.924526)
```
I thought it was the city names but it wasn't. I actually tried to zoom out a lil bit for each location and get the first highlighted word which I believe is either city or region then I googled for the string and the google autocorrect system helped.

flag:
```
picoCTF{KODIAK_ALASKA}
```
