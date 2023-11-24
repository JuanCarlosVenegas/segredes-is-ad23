## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt).
## Solución
```
┌──(kali㉿kali)-[~/Documents/3erExamen/parte2/bit1]
└─$ wget https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
--2023-11-24 13:08:27--  https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.64, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 209 [application/octet-stream]
Saving to: ‘disassembler-dump0_a.txt’

disassembler-dump0_a.txt     100%[==============================================>]     209  --.-KB/s    in 0s      

2023-11-24 13:08:29 (218 MB/s) - ‘disassembler-dump0_a.txt’ saved [209/209]

                                                                                                                    
┌──(kali㉿kali)-[~/Documents/3erExamen/parte2/bit1]
└─$ cat disassembler-dump0_a.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x4],edi
<+11>:    mov    QWORD PTR [rbp-0x10],rsi
<+15>:    mov    eax,0x30
<+20>:    pop    rbp
<+21>:    ret

Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(int("0x30", 16))
48

```
## Bandera
```
picoCTF{48}
```