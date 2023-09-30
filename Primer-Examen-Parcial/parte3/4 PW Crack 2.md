## Objetivo
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/14/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) in the same directory too.
## Solución 
```
charlyvr-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/14/level2.py
--2023-09-28 14:55:30--  https://artifacts.picoctf.net/c/14/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.71, 3.160.5.93, 3.160.5.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.71|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: 'level2.py'

level2.py                                      100%[====================================================================================================>]     914  --.-KB/s    in 0s      

2023-09-28 14:55:30 (42.1 MB/s) - 'level2.py' saved [914/914]

charlyvr-picoctf@webshell:~$ nano level2.py
charlyvr-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/14/level2.flag.txt.enc
--2023-09-28 14:56:45--  https://artifacts.picoctf.net/c/14/level2.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.93, 3.160.5.71, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level2.flag.txt.enc'

level2.flag.txt.enc                            100%[====================================================================================================>]      31  --.-KB/s    in 0s      

2023-09-28 14:56:45 (641 KB/s) - 'level2.flag.txt.enc' saved [31/31]

charlyvr-picoctf@webshell:~$ nano level2.flag.txt.enc 
charlyvr-picoctf@webshell:~$ nano level2.py
charlyvr-picoctf@webshell:~$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39) 
'4ec9'
>>> quit()
charlyvr-picoctf@webshell:~$ python3 level2.py 
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}
charlyvr-picoctf@webshell:~$ 
```
