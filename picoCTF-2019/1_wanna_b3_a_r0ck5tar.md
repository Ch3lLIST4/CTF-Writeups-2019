# 1_wanna_b3_a_r0ck5tar - Points: 350

## Problem
> I wrote you another [song](https://2019shell1.picoctf.com/static/ec882df63f9d0cfb8505879e0bc48c88/lyrics.txt). Put the flag in the picoCTF{} flag format

## Overview

Another rockstar challenge.


## Solutions

I just used [this website](https://codewithrockstar.com/online) just like the previous rockstar challenge. 

But now you'll notice that something's not right. Every time we hit compile and run, an alert box pops up. This is because it is asking for a user input. So we get rid of the ```Listen``` function and those ```if else``` functions that require the same variables.

```
Fixed code:

Rocknroll is right              
Silence is wrong                
A guitar is a six-string        
Tommy's been down               
Music is a billboard-burning razzmatazz!
                
Say "Keep on rocking!"                

Tommy is rockin guitar
Shout Tommy!                    
Music is amazing sensation 
Jamming is awesome presence
Scream Music!                   
Scream Jamming!                 
Tommy is playing rock           
Scream Tommy!       
They are dazzled audiences                  
Shout it!
Rock is electric heaven                     
Scream it!
Tommy is jukebox god            
Say it!                                     
Break it down
Shout "Bring on the rock!"
              
Break it down 
```
Click the button once again, there will be no alert box!
```
Output:
Keep on rocking!
66
79
78
74
79
86
73
```

Convert it to ASCII, we'll have:

```
BONJOVI
```

So, the flag is:
```
picoCTF{BONJOVI}
```
