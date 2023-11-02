## Objetivo
Decrypt this [message](https://jupiter.challenges.picoctf.org/static/6385b895dcb30c74dbd1f0ea271e3563/ciphertext).
## Solución
```
(kali㉿kali)-[~/Documents/cryptor1]
└─$ wget https://jupiter.challenges.picoctf.org/static/6385b895dcb30c74dbd1f0ea271e3563/ciphertext
--2023-11-01 20:27:56--  https://jupiter.challenges.picoctf.org/static/6385b895dcb30c74dbd1f0ea271e3563/ciphertext
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 35 [application/octet-stream]
Saving to: ‘ciphertext’

ciphertext                      100%[=====================================================>]      35  --.-KB/s    in 0s      

2023-11-01 20:28:05 (49.7 MB/s) - ‘ciphertext’ saved [35/35]

                                                                                                                              
┌──(kali㉿kali)-[~/Documents/cryptor1]
└─$ cat ciphertext 
picoCTF{dspttjohuifsvcjdpoabrkttds}  

lo que esta dentro de los {} vamos a copiar y pegarlo en la paguina que se encuentra abajo seleccionando rot13 y lo modificamos a rotación 25 y esa seria la bandera
```
## Bandera 
```
picoCTF{crossingtherubiconzaqjsscr}
```
## Referencias
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,25)&input=ZHNwdHRqb2h1aWZzdmNqZHBvYWJya3R0ZHM