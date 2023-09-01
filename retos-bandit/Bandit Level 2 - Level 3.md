## Bandit Level 2 - Level 3

## Objetivo
The password for the next level is stored in a file called **spaces in this filename** located in the home directory.
## Datos de acceso al nivel
```
bandit2 
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```
## Solución
```
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat spaces\ in\ this\ filename
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$
```
## Notas adicionales
Para ver el contenido de un archivo con espacios en el nombre hay que agregar una diagonal invertida en cada espacio.
## Referencias
