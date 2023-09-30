## Objetivo
Run the Python script and convert the given number from decimal to binary to get the flag. [Download Python script](https://artifacts.picoctf.net/c/23/convertme.py)
## Solución 
```
charlyvr-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/23/convertme.py
--2023-09-27 16:28:22--  https://artifacts.picoctf.net/c/23/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.93, 3.160.5.18, 3.160.5.71, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.93|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py                                   100%[====================================================================================================>]   1.16K  --.-KB/s    in 0s      

2023-09-27 16:28:22 (50.4 MB/s) - 'convertme.py' saved [1189/1189]

charlyvr-picoctf@webshell:~$ python3 convertme.py
If 68 is in decimal base, what is it in binary base?
Answer: 1000100
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_9c3b7d4d}
charlyvr-picoctf@webshell:~$ 
```
