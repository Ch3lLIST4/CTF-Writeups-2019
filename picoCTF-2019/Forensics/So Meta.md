# So Meta - Points: 150

## Problem

> Find the flag in this [picture](https://2019shell1.picoctf.com/static/ca487217eb5b5273f71c6b54f92d038d/pico_img.png). You can also find the file in /problems/so-meta_6_8d7541b8d04bd65a01336fdb8db6db24.

## Hints

> What does meta mean in the context of files?

> Ever hear of metadata?

## Overview

Looking at the title of the challenge, I was pretty sure this challenge's related to metadata in files.

## Solutions

I used a very common tool which is exiftool to check for metadata in the file.

```
$ exiftool pico_img.png

ExifTool Version Number         : 10.80
File Name                       : pico_img.png
Directory                       : .
File Size                       : 106 kB
File Modification Date/Time     : 2019:10:22 16:46:29+07:00
File Access Date/Time           : 2019:10:22 16:46:34+07:00
File Inode Change Date/Time     : 2019:10:22 16:46:29+07:00
File Permissions                : rwxrwxrwx
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Artist                          : picoCTF{s0_m3ta_505fdd8b}
Image Size                      : 600x600
Megapixels                      : 0.360
```

As you can see in the Artist section, the flag is:
```
picoCTF{s0_m3ta_505fdd8b}
```
