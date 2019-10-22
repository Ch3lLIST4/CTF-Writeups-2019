# vault-door-8

## Problem
> Apparently Dr. Evil's minions knew that our agency was making copies of their source code, because they intentionally sabotaged this source code in order to make it harder for our agents to analyze and crack into! The result is a quite mess, but I trust that my best special agent will find a way to solve it. The source code for this vault is here: [VaultDoor8.java](https://2019shell1.picoctf.com/static/58bc0f0cdd847bba9f9c3dd575fdcbc2/VaultDoor8.java)

## Hints

> Clean up the source code so that you can read it and understand what is going on.

> Draw a diagram to illustrate which bits are being switched in the scramble() method, then figure out a sequence of bit switches to undo it. You should be able to reuse the switchBits() method as is.

## Overview

As you can see the program takes a user input and see if its actually the flag or not.

Just reverse the entire function to see the required string which is also the flag.

## Solutions

My code:
```java
package test;
class Test {
 public static void main(String args[]) {
    Test a = new Test();
    char[] expected = {
        0xF4,0xC0,0x97,0xF0,0x77,0x97,0xC0,0xE4,0xF0,0x77,0xA4,
        0xD0,0xC5,0x77,0xF4,0x86,0xD0,0xA5,0x45,0x96,0x27,0xB5,
        0x77,0xF1,0xC1,0xF0,0x94,0xC1,0xA5,0xC1,0xC2,0xA4
    };
    String string = new String(expected);
    char[] descrambled = a.descrambled(string);
    String newString = new String(descrambled);
    
    System.out.println("The flag is: ");
    System.out.println(newString);
 }
 public char[] descrambled(String password) {
  /* Scramble a password by transposing pairs of bits. */
  char[] a = password.toCharArray();
  for (int b = 0; b < a.length; b++) {
   char c = a[b];
   c = switchBits(c, 6, 7);
   c = switchBits(c, 2, 5);
   c = switchBits(c, 3, 4);
   c = switchBits(c, 0, 1); /* d = switchBits(d, 4, 5); e = switchBits(e, 5, 6); */
   c = switchBits(c, 4, 7);
   c = switchBits(c, 5, 6);
   c = switchBits(c, 0, 3); /* c = switchBits(c,14,3); c = switchBits(c, 2, 0); */ 
   c = switchBits(c, 1, 2);
   a[b] = c;
  }
  return a;
 }
 public char switchBits(char c, int p1, int p2) {
  /* Move the bit in position p1 to position p2, and move the bit
  that was in position p2 to position p1. Precondition: p1 < p2 */
  char mask1 = (char)(1 << p1);
  char mask2 = (char)(1 << p2); /* char mask3 = (char)(1<<p1<<p2); mask1++; mask1--; */
  char bit1 = (char)(c & mask1);
  char bit2 = (char)(c & mask2);
  /* System.out.println("bit1 " + Integer.toBinaryString(bit1));
System.out.println("bit2 " + Integer.toBinaryString(bit2)); */
  char rest = (char)(c & ~(mask1 | mask2));
  char shift = (char)(p2 - p1);
  char result = (char)((bit1 << shift) | (bit2 >> shift) | rest);
  return result;
 }

}
```

Hit compile and run

```
Output:

run:
The flag is: 
s0m3_m0r3_b1t_sh1fTiNg_743a4f48b
BUILD SUCCESSFUL (total time: 0 seconds)
```

flag:
```
picoCTF{s0m3_m0r3_b1t_sh1fTiNg_743a4f48b}
```
