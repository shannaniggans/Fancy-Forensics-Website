---
title: Information
weight: 1
---
# Information

## Description
> Files can always be changed in a secret way. Can you find the flag?

## Method
Given that this is an image file the first tool that I used to analyse it was Exiftool.

```PowerShell
winget install OliverBetz.ExifTool
```

Once Exiftool was installed I simply pulled the metadata from the file:

```PowerShell
PS C:\Users\shanna\Downloads> ExifTool.exe .\cat.jpg
ExifTool Version Number         : 12.60
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
Zone Identifier                 : Exists
File Modification Date/Time     : 2023:10:24 02:44:50+00:00
File Access Date/Time           : 2023:10:24 03:22:27+00:00
File Creation Date/Time         : 2023:10:24 02:44:49+00:00
File Permissions                : -rw-rw-rw-
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
```

Taking a look at this the "License" line looks a bit strange, and could be an encoded string -> `cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9`.

To check, I used [CyberChef](https://gchq.github.io/CyberChef)

![CyberChef](<../../images/1_cyberchef.png>)

Looks like I found the flag:

{{< expand "Flag" "..." >}}
picoCTF{the_m3tadata_1s_modified}
{{< /expand >}}