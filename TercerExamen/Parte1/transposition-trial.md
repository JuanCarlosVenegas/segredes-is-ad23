## Objetivo
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message. Download the corrupted message [here](https://artifacts.picoctf.net/c/193/message.txt).
## Solución
```
kali㉿kali)-[~/Documents/3erExamen]
└─$ wget https://artifacts.picoctf.net/c/193/message.txt     
--2023-11-14 15:25:13--  https://artifacts.picoctf.net/c/193/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.26, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 54 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                                                100%[=======================================================================================================================================>]      54  --.-KB/s    in 0s      

2023-11-14 15:25:13 (61.1 MB/s) - ‘message.txt’ saved [54/54]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/3erExamen]
└─$ cat message.txt 
heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V9AAB1F8}7   
(kali㉿kali)-[~/Documents/3erExamen]
└─$ sudo nano trans.py

	FLAG = ""
	for i in range(0,len(MESSAGE),3):
	        FLAG += MESSAGE[i+2] + MESSAGE[i:i+2]
	
	print(FLAG)

(kali㉿kali)-[~/Documents/3erExamen]
└─$ python3 trans.py
The flag is picoCTF{7R4N5P051N6_15_3XP3N51V3_A9AFB178}
```
## Bandera
```
picoCTF{7R4N5P051N6_15_3XP3N51V3_A9AFB178}
```