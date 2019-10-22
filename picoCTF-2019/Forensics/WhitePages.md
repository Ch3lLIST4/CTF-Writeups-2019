# WhitePages - Points: 250

## Problem

> I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://2019shell1.picoctf.com/static/0c6da182a2b6eb85c909014da28377d5/whitepages.txt) is all blank!

## Overview

On the first look, it looked like the text file is empty. However, if we look closer, there are actually a very long string containing space characters. 
I did some investigation on these characters and I realized there are 2 types of space characters.

Using Javascript charCodeAt() method on them, I know that
* The first type has the value of ```8195```.
* The second one otherwise is ```32```.

These are probably binary values ```0``` and ```1```.

## Solutions

I built myself a script using Javascript.

```js
var fs = require('fs');
const string = fs.readFileSync('./whitepages.txt', 'utf8');

let charCodeArray = [];
for (var i = 0; i<string.length; i++) {
  charCodeArray[i] = string.charCodeAt(i);
}

charCode = charCodeArray.join('').replace(/8195/g, '0').replace(/32/g, '1').trim();


//bintoASCII
let stringArray = charCode.match(/.{1,8}/g);

let stringDecArray = [];

for (var i=0; i<stringArray.length ; i++){
  stringDecArray[i] = String.fromCharCode(parseInt(stringArray[i],2).toString(10));
}

console.log(stringDecArray.join(''));
```

Now let's run it using [nodejs](https://nodejs.org/en/) - omg I'm sorry I'm used to using JS over Python scripts xD.
```
Output:

>node solve.js

                picoCTF

                SEE PUBLIC RECORDS & BACKGROUND REPORT
                5000 Forbes Ave, Pittsburgh, PA 15213
                picoCTF{not_all_spaces_are_created_equal_c167040c738e8bcae2109ef4be5960b1}


```

flag:
```
picoCTF{not_all_spaces_are_created_equal_c167040c738e8bcae2109ef4be5960b1}
```
