# The Factory's Secret

## Problem
> There appear to be some mysterious glyphs hidden inside this [abandoned factory](https://2019game.picoctf.com/game)... I wonder what would happen if you collected them all?

## Hints
> Submit your answer in our competition's flag format. For example, if you answer was 'hello', you would submit 'picoCTF{hello}' as the flag.

## Overview

Not actually a challenge but it was pretty fun goin through, its a great introduction to CTF in general especially for beginners

There's nothing much to even talk about this challenge tbh, 

You just need to be wandering around the playfield on their game interface a lil bit and you'll end up finding all of the fragments that you'll need. You can find each from each room representing one of the categories.

Once you've found all of the fragments, you'll be able to find the password which is also the flag.

## Solutions

There are actually a few basic crypto challenges on the way and it might take you some time to figure out what you're even doing, but I believe it's not actually too hard for you on your way to find all of the fragments required.

Once you've collected all the fragments, you can see that its basically just QR code, so start scanning it using any QR scanning devices.

This is the result of the QR code:
```
password: xmfv53uqkf621gakvh502gxfu1g78glds
```

Use this password as the lost password to access the computer in the previous room, then you'll be able to see the secret conversation including the secret password as zerozerozerozero

So we know the answer for this challenge is,

flag:
```
picoCTF{zerozerozerozero}
```
