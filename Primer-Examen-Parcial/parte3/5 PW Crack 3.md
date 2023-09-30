## Objetivo 
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/18/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/18/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/18/level3.hash.bin) in the same directory too. There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Solución
```
charlyvr-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/18/level3.py
--2023-09-28 15:02:51--  https://artifacts.picoctf.net/c/18/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.93, 3.160.5.42, 3.160.5.71, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.93|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py                                      100%[====================================================================================================>]   1.31K  --.-KB/s    in 0s      

2023-09-28 15:02:51 (55.9 MB/s) - 'level3.py' saved [1337/1337]

charlyvr-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/18/level3.flag.txt.enc
--2023-09-28 15:03:11--  https://artifacts.picoctf.net/c/18/level3.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.42, 3.160.5.93, 3.160.5.71, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.enc                            100%[====================================================================================================>]      31  --.-KB/s    in 0s      

2023-09-28 15:03:11 (76.9 KB/s) - 'level3.flag.txt.enc' saved [31/31]

charlyvr-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/18/level3.hash.bin
--2023-09-28 15:03:22--  https://artifacts.picoctf.net/c/18/level3.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.93, 3.160.5.42, 3.160.5.71, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.93|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin                                100%[====================================================================================================>]      16  --.-KB/s    in 0s      

2023-09-28 15:03:22 (5.45 MB/s) - 'level3.hash.bin' saved [16/16]

charlyvr-picoctf@webshell:~$ nano level3.py
charlyvr-picoctf@webshell:~$ python3 level3.py
Please enter correct password for flag: 8799
That password is incorrect
charlyvr-picoctf@webshell:~$ python3 level3.py
Please enter correct password for flag: d3ab
That password is incorrect
charlyvr-picoctf@webshell:~$ python3 level3.py
Please enter correct password for flag: 1ea2
That password is incorrect
charlyvr-picoctf@webshell:~$ python3 level3.py
Please enter correct password for flag: acaf
That password is incorrect
charlyvr-picoctf@webshell:~$ python3 level3.py
Please enter correct password for flag: 2295
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_6f98a49f}
charlyvr-picoctf@webshell:~$ 
```
