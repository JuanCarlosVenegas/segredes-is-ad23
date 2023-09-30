## Objetivo
Fix the syntax error in this Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/25/fixme1.py)
## Solución 
```
charlyvr-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/25/fixme1.py
--2023-09-27 16:40:12--  https://artifacts.picoctf.net/c/25/fixme1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.18, 3.160.5.93, 3.160.5.71, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 837 [application/octet-stream]
Saving to: 'fixme1.py'

fixme1.py                                      100%[====================================================================================================>]     837  --.-KB/s    in 0s      

2023-09-27 16:40:12 (41.0 MB/s) - 'fixme1.py' saved [837/837]

charlyvr-picoctf@webshell:~$ nano fixme1.py
charlyvr-picoctf@webshell:~$ python fixme1.py 
import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5a) + chr(0x07) + chr(0x00) + chr(0x46) + chr(0x0b) + chr(0x1a) + chr(0x5a>

  
flag = str_xor(flag_enc, 'enkidu')
print('That is correct! Here\'s your flag: ' + flag)

That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_6a476c8f}
```
