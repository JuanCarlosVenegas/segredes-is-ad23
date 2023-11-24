## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).
## Solución
```
(kali㉿kali)-[~/Documents/3erExamen/parte2/bit2]
└─$ wget https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
--2023-11-24 13:13:06--  https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.100, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: ‘disassembler-dump0_b.txt’

disassembler-dump0_b.txt                                   100%[=======================================================================================================================================>]     270  --.-KB/s    in 0s      

2023-11-24 13:13:07 (281 MB/s) - ‘disassembler-dump0_b.txt’ saved [270/270]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/3erExamen/parte2/bit2]
└─$ cat disassembler-dump0_b.txt
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/3erExamen/parte2/bit2]
└─$ python3 
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(int("0x9fe1a",16))
654874

```
## Bandera
```
picoCTF{654874}
```