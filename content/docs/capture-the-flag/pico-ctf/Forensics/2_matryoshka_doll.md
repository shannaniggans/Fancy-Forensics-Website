---
title: Matryoshka doll
weight: 2
---
# Matryoshka doll

## Description
> Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one?

## Method
So the description and name of this one led me to think that maybe the file was potentially a compressed file, but once again used the `Exiftool` to take a look at the Metadata:

```PowerShell
PS C:\Users\shanna\Downloads> ExifTool.exe .\dolls.jpg
ExifTool Version Number         : 12.60
File Name                       : dolls.jpg
Directory                       : .
File Size                       : 652 kB
Zone Identifier                 : Exists
File Modification Date/Time     : 2023:10:24 03:46:35+00:00
File Access Date/Time           : 2023:10:24 03:48:46+00:00
File Creation Date/Time         : 2023:10:24 03:46:34+00:00
File Permissions                : -rw-rw-rw-
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 594
Image Height                    : 1104
Bit Depth                       : 8
Color Type                      : RGB with Alpha
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Profile Name                    : ICC Profile
Profile CMM Type                : Apple Computer Inc.
Profile Version                 : 2.1.0
Profile Class                   : Display Device Profile
Color Space Data                : RGB
Profile Connection Space        : XYZ
Profile Date Time               : 2020:06:09 12:08:45
Profile File Signature          : acsp
Primary Platform                : Apple Computer Inc.
CMM Flags                       : Not Embedded, Independent
Device Manufacturer             : Apple Computer Inc.
Device Model                    :
Device Attributes               : Reflective, Glossy, Positive, Color
Rendering Intent                : Perceptual
Connection Space Illuminant     : 0.9642 1 0.82491
Profile Creator                 : Apple Computer Inc.
Profile ID                      : 0
Profile Description             : Display
Profile Description ML (hr-HR)  : LCD u boji
Profile Description ML (ko-KR)  : ý╗¼Ùƒ¼ LCD
Profile Description ML (nb-NO)  : Farge-LCD
Profile Description ML (hu-HU)  : Sz├¡nes LCD
Profile Description ML (cs-CZ)  : Barevn├¢ LCD
Profile Description ML (da-DK)  : LCD-farvesk├ªrm
Profile Description ML (nl-NL)  : Kleuren-LCD
Profile Description ML (fi-FI)  : V├ñri-LCD
Profile Description ML (it-IT)  : LCD colori
Profile Description ML (es-ES)  : LCD color
Profile Description ML (ro-RO)  : LCD color
Profile Description ML (fr-CA)  : ACL couleur
Profile Description ML (uk-UA)  : ðÜð¥ð╗Ðîð¥ÐÇð¥ð▓ð©ð╣ LCD
Profile Description ML (he-IL)  : ÔÇÅLCD ÎªÎæÎóÎòÎáÎÖ
Profile Description ML (zh-TW)  : Õ¢®Þë▓LCD
Profile Description ML (vi-VN)  : LCD M├áu
Profile Description ML (sk-SK)  : Farebn├¢ LCD
Profile Description ML (zh-CN)  : Õ¢®Þë▓LCD
Profile Description ML (ru-RU)  : ðªð▓ðÁÐéð¢ð¥ð╣ ðûðÜ-ð┤ð©Ðüð┐ð╗ðÁð╣
Profile Description ML (en-GB)  : Colour LCD
Profile Description ML (fr-FR)  : LCD couleur
Profile Description ML (hi-IN)  : Óñ░ÓñéÓñùÓÑÇÓñ¿ LCD
Profile Description ML (th-TH)  : LCD Ó©¬Ó©Á
Profile Description ML (ca-ES)  : LCD en color
Profile Description ML (en-AU)  : Colour LCD
Profile Description ML (es-XL)  : LCD color
Profile Description ML (de-DE)  : Farb-LCD
Profile Description ML          : Color LCD
Profile Description ML (pt-BR)  : LCD Colorido
Profile Description ML (pl-PL)  : Kolor LCD
Profile Description ML (el-GR)  : ╬ê╬│¤ç¤ü¤ë╬╝╬À ╬┐╬©¤î╬¢╬À LCD
Profile Description ML (sv-SE)  : F├ñrg-LCD
Profile Description ML (tr-TR)  : Renkli LCD
Profile Description ML (pt-PT)  : LCD a Cores
Profile Description ML (ja-JP)  : Òé½Òâ®Òâ╝LCD
Profile Copyright               : Copyright Apple Inc., 2020
Media White Point               : 0.94955 1 1.08902
Red Matrix Column               : 0.51099 0.23955 -0.00104
Green Matrix Column             : 0.29517 0.69981 0.04224
Blue Matrix Column              : 0.15805 0.06064 0.78369
Red Tone Reproduction Curve     : (Binary data 2060 bytes, use -b option to extract)
Video Card Gamma                : (Binary data 48 bytes, use -b option to extract)
Native Display Info             : (Binary data 62 bytes, use -b option to extract)
Chromatic Adaptation            : 1.04861 0.02332 -0.05034 0.03018 0.99002 -0.01714 -0.00922 0.01503 0.75172
Make And Model                  : (Binary data 40 bytes, use -b option to extract)
Blue Tone Reproduction Curve    : (Binary data 2060 bytes, use -b option to extract)
Green Tone Reproduction Curve   : (Binary data 2060 bytes, use -b option to extract)
Exif Byte Order                 : Big-endian (Motorola, MM)
X Resolution                    : 144
Y Resolution                    : 144
Resolution Unit                 : inches
User Comment                    : Screenshot
Exif Image Width                : 594
Exif Image Height               : 1104
Pixels Per Unit X               : 5669
Pixels Per Unit Y               : 5669
Pixel Units                     : meters
XMP Toolkit                     : XMP Core 5.4.0
Apple Data Offsets              : (Binary data 28 bytes, use -b option to extract)
Warning                         : [minor] Trailer data after PNG IEND chunk
Image Size                      : 594x1104
Megapixels                      : 0.656
```

Few indicators:
* File Name is dolls.jpg, however the File Type in PNG.
* Warning: [minor] Trailer data after PNG IEND chunk. According to the [Exiftool reference site for PNG](https://exiftool.org/TagNames/PNG.html), *a PNG file should end at the IEND chunk* .... 

Knowing that there is more data, and having a feeling that this might be compressed (clued in from the name), I opened dolls.jpg with 7zip and found that it contained a folder and another image file: `2_c.jpg`, so I kept going in 7zip until I found `flag.txt`

![base_images](<../../images/2_7zip.png>)

Opening flag.txt gets me:
`p i c o C T F { b f 6 a c f 8 7 8 d c b d 7 5 2 f 4 7 2 1 e 4 1 b 1 b 1 b 6 6 b }`

Remove the extra white spaces....

{{< expand "Flag" ">" >}}
picoCTF{bf6acf878dcbd752f4721e41b1b1b66b}
{{< /expand >}}

Alternatively you can use `unzip`

```shell
shanna@khaleesi:/mnt/c/Users/frenz/Downloads$ unzip .\dolls.jpg
unzip:  cannot find or open .dolls.jpg, .dolls.jpg.zip or .dolls.jpg.ZIP.
shanna@khaleesi:/mnt/c/Users/frenz/Downloads$ unzip dolls.jpg
Archive:  dolls.jpg
warning [dolls.jpg]:  272492 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/2_c.jpg
shanna@khaleesi:/mnt/c/Users/frenz/Downloads$ unzip base_images/2_c.jpg
Archive:  base_images/2_c.jpg
warning [base_images/2_c.jpg]:  187707 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/3_c.jpg
shanna@khaleesi:/mnt/c/Users/frenz/Downloads$ unzip base_images/3_c.jpg
Archive:  base_images/3_c.jpg
warning [base_images/3_c.jpg]:  123606 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/4_c.jpg
shanna@khaleesi:/mnt/c/Users/frenz/Downloads$ unzip base_images/4_c.jpg
Archive:  base_images/4_c.jpg
warning [base_images/4_c.jpg]:  79578 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: flag.txt
shanna@khaleesi:/mnt/c/Users/frenz/Downloads$ cat flag.txt
picoCTF{bf6acf878dcbd752f4721e41b1b1b66b}
```