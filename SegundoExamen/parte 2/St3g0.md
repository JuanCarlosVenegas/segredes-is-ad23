## Objetivo
Download this image and find the flag.

- [Download image](https://artifacts.picoctf.net/c/215/pico.flag.png)
## Solución
```
                                                                                                                       
┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/215/pico.flag.png                             
--2023-11-04 15:45:35--  https://artifacts.picoctf.net/c/215/pico.flag.png
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.119, 18.160.124.34, 18.160.124.108, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.119|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 13438 (13K) [application/octet-stream]
Saving to: ‘pico.flag.png’

pico.flag.png                 100%[================================================>]  13.12K  --.-KB/s    in 0s      

2023-11-04 15:45:45 (160 MB/s) - ‘pico.flag.png’ saved [13438/13438]

                                                                                                                       
┌──(kali㉿kali)-[~]
└─$ exiftool pico.flag.png _img.png
======== pico.flag.png
ExifTool Version Number         : 12.65
File Name                       : pico.flag.png
Directory                       : .
File Size                       : 13 kB
File Modification Date/Time     : 2023:08:04 14:36:13-06:00
File Access Date/Time           : 2023:11:04 15:45:45-06:00
File Inode Change Date/Time     : 2023:11:04 15:45:45-06:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 585
Image Height                    : 172
Bit Depth                       : 8
Color Type                      : RGB with Alpha
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Image Size                      : 585x172
Megapixels                      : 0.101
Error: File not found - _img.png
    1 image files read
    1 files could not be read
                                                                                                                       
┌──(kali㉿kali)-[~]
└─$ sudo gem install zsteg                               
[sudo] password for kali: 
Fetching zsteg-0.2.13.gem
Fetching zpng-0.4.5.gem
Fetching rainbow-3.1.1.gem
Successfully installed rainbow-3.1.1
Successfully installed zpng-0.4.5
Successfully installed iostruct-0.0.5
Successfully installed zsteg-0.2.13
Parsing documentation for rainbow-3.1.1
Installing ri documentation for rainbow-3.1.1
Parsing documentation for zpng-0.4.5
Installing ri documentation for zpng-0.4.5
Parsing documentation for iostruct-0.0.5
Installing ri documentation for iostruct-0.0.5
Parsing documentation for zsteg-0.2.13
Installing ri documentation for zsteg-0.2.13
Done installing documentation for rainbow, zpng, iostruct, zsteg after 1 seconds
4 gems installed
(kali㉿kali)-[~]
└─$ zsteg pico.flag.png 
b1,r,lsb,xy         .. text: "~__B>wV_G@"
b1,rgb,lsb,xy       .. text: "picoCTF{7h3r3_15_n0_5p00n_96ae0ac1}$t3g0"
b1,abgr,lsb,xy      .. text: "E2A5q4E%uSA"
b2,b,lsb,xy         .. text: "AAPAAQTAAA"
b2,b,msb,xy         .. text: "HWUUUUUU"
b3,r,lsb,xy         .. file: gfxboot compiled html help file
b4,r,lsb,xy         .. file: Targa image data (16-273) 65536 x 4097 x 1 +4352 +4369 - 1-bit alpha - right "\021\020\001\001\021\021\001\001\021\021\001"                                                                                      
b4,g,lsb,xy         .. file: 0420 Alliant virtual executable not stripped
b4,b,lsb,xy         .. file: Targa image data - Map 272 x 17 x 16 +257 +272 - 1-bit alpha "\020\001\021\001\021\020\020\001\020\001\020\001"                                                                                                  
b4,bgr,lsb,xy       .. file: Targa image data - Map 273 x 272 x 16 +1 +4113 - 1-bit alpha "\020\001\001\001"
b4,rgba,msb,xy      .. file: Applesoft BASIC program data, first line number 8
                                                                                                                       
┌──(kali㉿kali)-[~]
└─$ 

```
## Bandera
```
picoCTF{7h3r3_15_n0_5p00n_96ae0ac1}
```