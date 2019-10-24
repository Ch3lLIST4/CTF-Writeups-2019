# shark on wire 1 - Points: 150

## Problem

> We found this [packet capture](https://2019shell1.picoctf.com/static/ae9ca8cff43ed638ed5d137f9ece7455/capture.pcap). Recover the flag. You can also find the file in /problems/shark-on-wire-1_0_13d709ec13952807e477ba1b5404e620.

## Hints

> Try using a tool like Wireshark

> What are streams?

## Overview

They hand us a pcap file, so obviously imma open it using wireshark. Let's analyze these network traffics.

## Solutions

As the hint said, we would check the stream first. Go to Analyze and follow UDP stream.

Simple as that, I found the flag at stream 6.

-----

flag:
```
picoCTF{StaT31355_636f6e6e}
```
