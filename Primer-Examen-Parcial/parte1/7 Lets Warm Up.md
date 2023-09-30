## Objetivo
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

## Solucion 
```
charlyvr-picoctf@webshell:~$ python
Python 3.10.6 (main, Aug 10 2022, 11:38:12) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> int (0x70)
112
>>> chr(112)
'p'
>>> chr(0x70)
'p'
>>
picoCTF{p}
```


