## Objetivo
Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/d6f9aa16d2a2c51d2e431e658d87af9e/shark1.pcapng).
## Solución
```
Para este retp tenemos que abrir el archivo que nos da el reto con el explorador de archivos Wireshark y scrolear hasta abajo hasta encontrar este archivo:
823	7.187055	192.168.38.104	18.222.37.134	HTTP	501	GET / HTTP/1.1 
Damos click derecho en el, 'follow', 'HTML'
nos abrira dos ventanas nuevas, en una de ellas veremos a bandera pero con rot13
la copiamos y la pegamos en el siguiente URL:
https://rot13.com/
Y nos dara la bandera
```
## Bandera
```
picoCTF{p33kab00_1_s33_u_deadbeef}
```