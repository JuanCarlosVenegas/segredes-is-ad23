## Objetivo
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/static)? This [BASH script](https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/ltdis.sh) might help!
## Solución
```
charlyvr-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/static
--2023-09-25 17:11:18--  https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/static
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8376 (8.2K) [application/octet-stream]
Saving to: 'static.1'

static.1                                       100%[====================================================================================================>]   8.18K  --.-KB/s    in 0s      

2023-09-25 17:11:18 (233 MB/s) - 'static.1' saved [8376/8376]
charlyvr-picoctf@webshell:~$ chmod +x static
charlyvr-picoctf@webshell:~$ ./static
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
charlyvr-picoctf@webshell:~$ strings static | grep pico
picoCTF{d15a5m_t34s3r_ccb2b43e}
charlyvr-picoctf@webshell:~$ 
```