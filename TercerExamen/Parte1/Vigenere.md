## Objetivo
Can you decrypt this message? Decrypt this [message](https://artifacts.picoctf.net/c/158/cipher.txt) using this key "CYLAB".
## Solución
```
(kali㉿kali)-[~/Documents/3erExamen/vigenere]
└─$ wget https://artifacts.picoctf.net/c/158/cipher.txt 
--2023-11-14 15:44:27--  https://artifacts.picoctf.net/c/158/cipher.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.26, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43 [application/octet-stream]
Saving to: ‘cipher.txt’

cipher.txt                                                 100%[=======================================================================================================================================>]      43  --.-KB/s    in 0s      

2023-11-14 15:44:28 (107 MB/s) - ‘cipher.txt’ saved [43/43]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/3erExamen/vigenere]
└─$ cat cipher.txt 
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_cc82272b}

```
## Bandera
```
picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_ae82272q}
```
## Referencias 
https://www.dcode.fr/vigenere-cipher