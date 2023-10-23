## Objetivo
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/9a7436948cc502e9cacf5bc84d2cccb5/Forensics is fun.pptm)
## Solución
``` 
(kali㉿kali)-[~/Documents/pico-3/MacroHardWeakEdge]
└─$ wget 'https://mercury.picoctf.net/static/9a7436948cc502e9cacf5bc84d2cccb5/Forensics is fun.pptm'
--2023-10-23 01:58:41--  https://mercury.picoctf.net/static/9a7436948cc502e9cacf5bc84d2cccb5/Forensics%20is%20fun.pptm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 100093 (98K) [application/octet-stream]
Saving to: ‘Forensics is fun.pptm’

Forensics is fun.pptm        100%[============================================>]  97.75K  --.-KB/s    in 0.1s    

2023-10-23 01:58:50 (744 KB/s) - ‘Forensics is fun.pptm’ saved [100093/100093]

                                                                                                                  
┌──(kali㉿kali)-[~/Documents/pico-3/MacroHardWeakEdge]
└─$ file Forensics\ is\ fun.pptm 
Forensics is fun.pptm: Microsoft PowerPoint 2007+
                                                                                                                  
┌──(kali㉿kali)-[~/Documents/pico-3/MacroHardWeakEdge]
└─$ ls -la
total 108
drwxr-xr-x 2 kali kali   4096 Oct 23 01:58  .
drwxr-xr-x 6 kali kali   4096 Oct 23 01:43  ..
-rw-r--r-- 1 kali kali 100093 Mar 23  2021 'Forensics is fun.pptm'
                                                                                                                  
┌──(kali㉿kali)-[~/Documents/pico-3/MacroHardWeakEdge]
└─$ unzip Forensics\ is\ fun.pptm 
(kali㉿kali)-[~/Downloads]
└─$ sudo dpkg -i code_1.83.1-1696982868_amd64.deb
Selecting previously unselected package code.
(Reading database ... 398597 files and directories currently installed.)
Preparing to unpack code_1.83.1-1696982868_amd64.deb ...
Unpacking code (1.83.1-1696982868) ...
Setting up code (1.83.1-1696982868) ...
Processing triggers for desktop-file-utils (0.26-1) ...
Processing triggers for mailcap (3.70+nmu1) ...
Processing triggers for shared-mime-info (2.2-1) ...
                                                                                                                  
┌──(kali㉿kali)-[~/Downloads]
└─$ cd ..       
                                                                                                                  
┌──(kali㉿kali)-[~]
└─$ cd Documents/pico-3/MacroHardWeakEdge
                                                                                                                  
┌──(kali㉿kali)-[~/Documents/pico-3/MacroHardWeakEdge]
└─$ code .                                       
                                                                                                                  
┌──(kali㉿kali)-[~/Documents/pico-3/MacroHardWeakEdge]
└─$ echo "Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q" | tr -d " " | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: invalid input

```
## Bandera 
``` 
picoCTF{D1d_u_kn0w_ppts_r_z1p5}
```