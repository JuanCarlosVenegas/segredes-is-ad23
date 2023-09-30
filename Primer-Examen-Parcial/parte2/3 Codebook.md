## Objetivo
#### Description

Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/2/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/2/codebook.txt)
## Solución
```
charlyvr-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/2/code.py
--2023-09-27 16:17:44--  https://artifacts.picoctf.net/c/2/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.71, 3.160.5.93, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.71|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py.2'

code.py.2                                      100%[====================================================================================================>]   1.25K  --.-KB/s    in 0s      

2023-09-27 16:17:45 (35.9 MB/s) - 'code.py.2' saved [1278/1278]

charlyvr-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/2/codebook.txt
--2023-09-27 16:17:56--  https://artifacts.picoctf.net/c/2/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.42, 3.160.5.71, 3.160.5.93, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt.2'

codebook.txt.2                                 100%[====================================================================================================>]      27  --.-KB/s    in 0s      

2023-09-27 16:17:56 (1.26 MB/s) - 'codebook.txt.2' saved [27/27]
charlyvr-picoctf@webshell:~$ python3 code.py.2 
picoCTF{c0d3b00k_455157_7d102d7a}
```
