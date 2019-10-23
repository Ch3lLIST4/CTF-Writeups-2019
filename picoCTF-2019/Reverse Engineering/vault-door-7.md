# vault-door-7 - Points: 400

## Problem

> This vault uses bit shifts to convert a password string into an array of integers. Hurry, agent, we are running out of time to stop Dr. Evil's nefarious plans! The source code for this vault is here: [VaultDoor7.java](https://2019shell1.picoctf.com/static/9fc4e47b7a5f925b7f7230b4b3ef2d90/VaultDoor7.java)

## Hints

> Use a decimal/hexademical converter such as this one: https://www.mathsisfun.com/binary-decimal-hexadecimal-converter.html

> You will also need to consult an ASCII table such as this one: https://www.asciitable.com/

## Overview

As you can see the program takes a user input and see if its actually the flag or not.

Just reverse the entire function to see the required string which is also the flag.

## Solutions

My code:
```java
package test;

public class Test {
    public static void main(String args[]) {
        Test vaultDoor = new Test();

        vaultDoor.passwordToIntArray();
    }

    public int[] passwordToIntArray() {
        int[] x = new int[8];
        x[0] = 1096770097;
        x[1] = 1952395366;
        x[2] = 1600270708;
        x[3] = 1601398833;
        x[4] = 1716808014;
        x[5] = 1734305381;
        x[6] = 828716089;
        x[7] = 895562083;
        byte[] hexBytes = new byte[50];
        for (int i=0; i<8; i++) {
                 hexBytes[i*4] = (byte) (x[i]  >> 24);
                 hexBytes[i*4+1] = (byte) (x[i] >> 16);
                 hexBytes[i*4+2] = (byte) (x[i] >> 8);
                 hexBytes[i*4+3] = (byte) x[i];
        }
        String s = new String(hexBytes);
        System.out.println(s);
        return x;
    }

}
```
Hit compile and run
```
run:
A_b1t_0f_b1t_sh1fTiNg_fe1e495a1c
```

flag:
```
picoCTF{A_b1t_0f_b1t_sh1fTiNg_fe1e495a1c}
```
