## Objetivo
What does asm2(0x4,0x21) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/7e3eb2f90200ac88126f62ceb4bc3948/test.S)
## Solución
```
(kali㉿kali)-[~/Documents/reversing2]
└─$ wget https://jupiter.challenges.picoctf.org/static/7e3eb2f90200ac88126f62ceb4bc3948/test.S    
--2023-11-13 15:45:50--  https://jupiter.challenges.picoctf.org/static/7e3eb2f90200ac88126f62ceb4bc3948/test.S
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 478 [application/octet-stream]
Saving to: ‘test.S.1’

test.S.1                     100%[============================================>]     478  --.-KB/s    in 0s      

2023-11-13 15:45:51 (14.0 MB/s) - ‘test.S.1’ saved [478/478]

                                                                                                                  
┌──(kali㉿kali)-[~/Documents/reversing2]
└─$ cat test.S.1  
asm2:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   sub    esp,0x10
        <+6>:   mov    eax,DWORD PTR [ebp+0xc]
        <+9>:   mov    DWORD PTR [ebp-0x4],eax
        <+12>:  mov    eax,DWORD PTR [ebp+0x8]
        <+15>:  mov    DWORD PTR [ebp-0x8],eax
        <+18>:  jmp    0x509 <asm2+28>
        <+20>:  add    DWORD PTR [ebp-0x4],0x1
        <+24>:  add    DWORD PTR [ebp-0x8],0x74
        <+28>:  cmp    DWORD PTR [ebp-0x8],0xfb46
        <+35>:  jle    0x501 <asm2+20>
        <+37>:  mov    eax,DWORD PTR [ebp-0x4]
        <+40>:  leave  
        <+41>:  ret

stack 

[    ] < esp
[    ] < ebp-0xc
[0x78] < ebp-0x8
[0x22] < ebp-0x4
[ebp ] < esp
[ret ] < ebp+0x4
[0x4 ] < ebp+0x8
[0x21] < ebp+0xc

registers
[0x24c] eax
-----------------------------------------------
asm2: (0x4,0x21)
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   sub    esp,0x10
        <+6>:   mov    eax,DWORD PTR [ebp+0xc]
        <+9>:   mov    DWORD PTR [ebp-0x4],eax
        <+12>:  mov    eax,DWORD PTR [ebp+0x8]
        <+15>:  mov    DWORD PTR [ebp-0x8],eax
        <+18>:  jmp    0x509 <asm2+28>
        <+20>:  add    DWORD PTR [ebp-0x4],0x1
        <+24>:  add    DWORD PTR [ebp-0x8],0x74
        <+28>:  cmp    DWORD PTR [ebp-0x8],0xfb46
        <+35>:  jle    0x501 <asm2+20>
        <+37>:  mov    eax,DWORD PTR [ebp-0x4]
        <+40>:  leave  
        <+41>:  ret    

(kali㉿kali)-[~]
└─$ python3
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x4 <= 0xfb46
True
>>> hex(0x21+0x1)
'0x22'
>>> hex(0x4 + 0x74)
'0x78'
>>> 0x78 <= 0xfb46
True
>>> 0xfb46 / 0x74
554.5344827586207
>>> int(0x21)
33
>>> hex(33 + 555)
'0x24c'

```
## Bandera
```
0x24c
```