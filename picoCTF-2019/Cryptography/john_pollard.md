# john_pollard - Points: 500

## Problem

> Sometimes RSA [certificates](https://2019shell1.picoctf.com/static/ccd7ba84ead965bd2033a54c4dbb8ae0/cert) are breakable

## Hints

> The flag is in the format picoCTF{p,q}

> Try swapping p and q if it does not work

## Overview

They give us a cert file and obviously this is PEM certificate file type
```
$ file cert
cert: PEM certificate
```

Based on the hints, we just simply need to extract p and q values from this pem.

## Solutions

Let's extract the public key first from the attached certificate:
```
$ openssl x509 -pubkey -noout -in cert > ke
y.pub
```
Now we have the RSA public key 
```
$ ls
cert  key.pub
```
Let's see what we can extract from it
```
$ openssl rsa -pubin -in key.pub -text
RSA Public-Key: (53 bit)
Modulus: 4966306421059967 (0x11a4d45212b17f)
Exponent: 65537 (0x10001)
writing RSA key
-----BEGIN PUBLIC KEY-----
MCIwDQYJKoZIhvcNAQEBBQADEQAwDgIHEaTUUhKxfwIDAQAB
-----END PUBLIC KEY-----
```

This Modulus (n) looks pretty short, I decided to extract p and q using a script. Luckily i found a [function](https://stackoverflow.com/questions/40200089/number-prime-test-in-javascript) for prime checking
```js
//guess primes from modulus
// isPrime ?
const isPrime = num => {
  for(let i = 2; i < num; i++)
    if(num % i === 0) return false;
  return num > 1;
}

const n = 4966306421059967;

for (i = 0 ; i<n; i++){
  if (n % i === 0 && isPrime(i) && isPrime(n/i)) {
    console.log("i:" + i);
    console.log("n/i:" + n/i);
    break;
  }
}
```
Run it using [nodejs](https://nodejs.org)
```
Output:
>node guess.js
i:67867967
n/i:73176001
```

I tried ```picoCTF{67867967,73176001}``` But it wasn't correct. Therefore, the correct one should be:

flag:
```
picoCTF{73176001,67867967}
```
