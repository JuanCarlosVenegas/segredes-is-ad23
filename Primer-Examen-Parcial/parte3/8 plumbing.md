## Objetivo
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 7480`.
## Solución
```
charlyvr-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 7480 > bandera.txt

charlyvr-picoctf@webshell:~$ ls
README.txt  bandera.txt  fixme2.py  level2.flag.txt.enc  level2.py  level3.flag.txt.enc  level3.hash.bin  level3.py  runme.py
charlyvr-picoctf@webshell:~$ cat bandera.txt | grep picoCTF*
picoCTF{digital_plumb3r_06e9d954}
charlyvr-picoctf@webshell:~$ 
```