## Objetivo
Can you get the flag? Here's the [website](http://saturn.picoctf.net:58179/). We know that the website files live in `/usr/share/nginx/html/` and the flag is at `/flag.txt` but the website is filtering absolute file paths. Can you get past the filter to read the flag?
## Solución
```
Para este reto lo que tenemos que hacer es abrir en una pestana el link que nos proporciona el reto y poner lo siguiente en el cuadro que nos aparece para poner texto: ../../../../flag.txt
```
## Bandera
```
picoCTF{7h3_p47h_70_5ucc355_6db46514}
```