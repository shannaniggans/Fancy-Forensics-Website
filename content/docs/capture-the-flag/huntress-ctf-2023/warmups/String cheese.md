---
title: "String cheese"
weight: 50
---
## String cheese

> Oh, a cheese stick! This was my favorite snack as a kid. My mom always called it by a different name though...

For this challenge we are provided with `cheese.jpg`. Given it an image the first thing I did was run exiftool just to check.

```shell
exiftool cheese.jpg
ExifTool Version Number         : 12.40
File Name                       : cheese.jpg
Directory                       : .
File Size                       : 34 KiB
File Modification Date/Time     : 2023:10:24 23:53:03+00:00
File Access Date/Time           : 2023:10:25 08:19:57+00:00
File Inode Change Date/Time     : 2023:10:25 08:17:00+00:00
File Permissions                : -rwxrwxrwx
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 300
Y Resolution                    : 300
Exif Byte Order                 : Little-endian (Intel, II)
Image Description               : string cheese isolated on white
Copyright                       : Diana Taliun
Rights                          : Diana Taliun
Asset ID                        : 626338818
Web Statement                   : https://www.istockphoto.com/legal/license-agreement?utm_medium=organic&utm_source=google&utm_campaign=iptcurl
Creator                         : Diana Taliun
Description                     : string cheese isolated on white
Licensor URL                    : https://www.istockphoto.com/photo/license-gm626338818-?utm_medium=organic&utm_source=google&utm_campaign=iptcurl
Current IPTC Digest             : 8ddf79d1f57aa349c8ca4cdda9aa8277
By-line                         : Diana Taliun
Caption-Abstract                : string cheese isolated on white
Copyright Notice                : Diana Taliun
Credit                          : Getty Images/iStockphoto
Image Width                     : 612
Image Height                    : 408
Encoding Process                : Progressive DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:4:4 (1 1)
Image Size                      : 612x408
Megapixels                      : 0.250
```

OK, so yeah image file, but why is an image file have execute permissions? Anyway, having done a few CTFs before I went straight to strings:

```shell
$ strings cheese.jpg | grep flag
flag{f4d9f0f70bf353f2ca23d81dcf7c9099}
```

Whallah

{{< details "Flag" ">" >}}
flag{f4d9f0f70bf353f2ca23d81dcf7c9099}
{{< /details >}}