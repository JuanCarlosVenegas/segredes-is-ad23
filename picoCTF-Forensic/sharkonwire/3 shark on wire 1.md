## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.
## Solución
```
Tenemos que descargar el archivo que nos da el reto y abrirlo en un sistema operativo Linux, abriremos el whireshark y abrimos el archivo descargado, le damos click derecho en cualquier protocolo UDP, y en el stream saldra 4 y lo vamos a subir hasta que aparezca la bandera en este caso el 6.
```
## Bandera 
```
picoCTF{StaT31355_636f6e6e}
```