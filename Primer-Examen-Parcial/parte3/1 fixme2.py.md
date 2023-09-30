## Objetivo
Fix the syntax error in the Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/6/fixme2.py)
## Solución
```
charlyvr-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/6/fixme2.py
--2023-09-27 16:56:37--  https://artifacts.picoctf.net/c/6/fixme2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.93, 3.160.5.42, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.93|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1029 (1.0K) [application/octet-stream]
Saving to: 'fixme2.py'

fixme2.py                                      100%[====================================================================================================>]   1.00K  --.-KB/s    in 0s      

2023-09-27 16:56:37 (207 MB/s) - 'fixme2.py' saved [1029/1029]

charlyvr-picoctf@webshell:~$ ls
file  fixme1.py  fixme2.py  strings
charlyvr-picoctf@webshell:~$ nano fixme2.py 
charlyvr-picoctf@webshell:~$ python3 fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}
```
