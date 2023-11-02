## Objetivo
The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?
## Solución
```
(kali㉿kali)-[~/Documents/Crypto1/TheNumbers]
└─$ wget https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
--2023-10-25 10:25:11--  https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 100721 (98K) [application/octet-stream]
Saving to: ‘the_numbers.png’

the_numbers.png                 100%[=====================================================>]  98.36K   605KB/s    in 0.2s    

2023-10-25 10:25:20 (605 KB/s) - ‘the_numbers.png’ saved [100721/100721]

                                                                                                                              
┌──(kali㉿kali)-[~/Documents/Crypto1/TheNumbers]
└─$ open the_numbers.png 

Cambiamos los numeros por la posición del alfabeto y nos da la bandera
```
## Bandera 
```
picoCFT{thenumbersmason}
```
