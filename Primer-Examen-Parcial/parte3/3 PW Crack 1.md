## Objetivo
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/12/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/12/level1.flag.txt.enc) in the same directory too.
## Solución 
```
charlyvr-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/12/level1.py
--2023-09-28 14:45:35--  https://artifacts.picoctf.net/c/12/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.42, 3.160.5.18, 3.160.5.71, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py                                      100%[====================================================================================================>]     876  --.-KB/s    in 0s      

2023-09-28 14:45:35 (613 MB/s) - 'level1.py' saved [876/876]

charlyvr-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
--2023-09-28 14:46:01--  https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.71, 3.160.5.93, 3.160.5.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.71|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc                            100%[====================================================================================================>]      30  --.-KB/s    in 0s      

2023-09-28 14:46:01 (1.20 MB/s) - 'level1.flag.txt.enc' saved [30/30]
charlyvr-picoctf@webshell:~$ cat level1.flag.txt.enc
[gE]__TgS^S

           Jcharlyvr-picoctf@webshell:~$ nano level1.flag.txt.enc
charlyvr-picoctf@webshell:~$ nano level1.py 
charlyvr-picoctf@webshell:~$ python3 level1.py 
Please enter correct password for flag: 8713
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_1b2fd683}
charlyvr-picoctf@webshell:~$ 
```
