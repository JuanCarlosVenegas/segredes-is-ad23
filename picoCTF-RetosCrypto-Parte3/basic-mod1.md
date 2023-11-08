
## Objetivo
We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message [here](https://artifacts.picoctf.net/c/127/message.txt). Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
## Solución
```
                                                                                                                                          
┌──(kali㉿kali)-[~/hacking/cryptor3]
└─$ wget https://artifacts.picoctf.net/c/127/message.txt
--2023-11-08 10:44:26--  https://artifacts.picoctf.net/c/127/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.108, 18.160.124.38, 18.160.124.34, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.108|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 85 [application/octet-stream]
Saving to: ‘message.txt.1’

message.txt.1                      100%[==============================================================>]      85  --.-KB/s    in 0s      

2023-11-08 10:44:41 (131 MB/s) - ‘message.txt.1’ saved [85/85]

                                                                                                                                          
┌──(kali㉿kali)-[~/hacking/cryptor3]
└─$ cat message.txt                                     
128 322 353 235 336 73 198 332 202 285 57 87 262 221 218 405 335 101 256 227 112 140                                                                                                                                           
┌──(kali㉿kali)-[~/hacking/cryptor3]
└─$ nano exp.py 

datos = open('message.txt').read().split()

print (datos)

flag = ''

for n in datos:
     c = int(n) % 37
     if c>=0 and c <=25:
        s = chr(c+65)
     elif c >= 25 and c <= 35:
        s = chr(c+22)
     else:
        s = '_'
     flag += s
print(f"picoCTF{{{flag}}}")

┌──(kali㉿kali)-[~/hacking/cryptor3]
└─$ python3 exp.py
['128', '322', '353', '235', '336', '73', '198', '332', '202', '285', '57', '87', '262', '221', '218', '405', '335', '101', '256', '227', '112', '140']
picoCTF{R0UND_N_R0UND_79C18FB3}
```
## Bandera
```
picoCTF{R0UND_N_R0UND_79C18FB3}
```