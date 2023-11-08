## Objetivo
How about some hide and seek heh? Look at this image [here](https://artifacts.picoctf.net/c/235/atbash.jpg).
## Solución
```
(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/235/atbash.jpg                                           
--2023-11-08 10:50:17--  https://artifacts.picoctf.net/c/235/atbash.jpg
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.119, 18.160.124.34, 18.160.124.108, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.119|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 51499 (50K) [application/octet-stream]
Saving to: ‘atbash.jpg’

atbash.jpg                   100%[=============================================>]  50.29K  --.-KB/s    in 0.09s   

2023-11-08 10:50:26 (551 KB/s) - ‘atbash.jpg’ saved [51499/51499]

                                                                                                                   
┌──(kali㉿kali)-[~]
└─$ open atbash.jpg 


una vez abierta la imagen nos vamos al siguiente URL: [https://futureboy.us/stegano/decinput.html](https://futureboy.us/stegano/decinput.html) Ponemos la imagen q bajamos y nos dará lo siguiente: krxlXGU{zgyzhs_xizxp_05y2z65z} Ahora nos vamos a la siguiente URL: [https://www.dcode.fr/atbash-cipher](https://www.dcode.fr/atbash-cipher) y colocamos lo que nos salio y nos dará la respuesta: picoCTF{atbash_crack_92533667}
```
## Bandera
```
picoCTF{atbash_crack_92533667}
```

