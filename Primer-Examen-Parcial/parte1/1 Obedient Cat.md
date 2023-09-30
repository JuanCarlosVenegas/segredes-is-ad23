## Objetivo
This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/fb851c1858cc762bd4eed569013d7f00/flag).
## Solución
```
charlyvr-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/fb851c1858cc762bd4eed569013d7f00/flag
--2023-09-25 16:51:40--  https://mercury.picoctf.net/static/fb851c1858cc762bd4eed569013d7f00/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag.2'

flag.2                                         100%[====================================================================================================>]      34  --.-KB/s    in 0s      

2023-09-25 16:51:40 (17.9 MB/s) - 'flag.2' saved [34/34]

charlyvr-picoctf@webshell:~$ cat flag
picoCTF{s4n1ty_v3r1f13d_28e8376d}
charlyvr-picoctf@webshell:~$ 
```
## Notas adicionales
## Referencias
