## Bandit Level 5 - Level 6

## Objetivo
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable
## Datos de acceso al nivel
bandit5 
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
## Solución
```
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15  maybehere18
maybehere01  maybehere04  maybehere07  maybehere10  maybehere13  maybehere16  maybehere19
maybehere02  maybehere05  maybehere08  maybehere11  maybehere14  maybehere17
bandit5@bandit:~/inhere$ find . -readable -type -size 1033c
find: Unknown argument to -type: -
bandit5@bandit:~/inhere$ find . -readable -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/
-file1        -file2        -file3        spaces file1  spaces file3
.file1        .file2        .file3        spaces file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```
## Notas adicionales
## Referencias
