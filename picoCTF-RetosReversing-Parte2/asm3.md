## Objetivo
What does asm3(0xd2c26416,0xe6cf51f0,0xe54409d5) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/df999527eaecf46f259c4337a820856c/test.S)
## Solución
```
(kali㉿kali)-[~/Documents/reversing2]
└─$ wget https://jupiter.challenges.picoctf.org/static/df999527eaecf46f259c4337a820856c/test.S    
--2023-11-13 16:55:10--  https://jupiter.challenges.picoctf.org/static/df999527eaecf46f259c4337a820856c/test.S
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 286 [application/octet-stream]
Saving to: ‘test.S.2’

test.S.2                     100%[============================================>]     286  --.-KB/s    in 0s      

2023-11-13 16:55:11 (6.83 MB/s) - ‘test.S.2’ saved [286/286]

                                                                                                                  
┌──(kali㉿kali)-[~/Documents/reversing2]
└─$ cat test.S.2 
asm3:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   xor    eax,eax
        <+5>:   mov    ah,BYTE PTR [ebp+0x9]
        <+8>:   shl    ax,0x10
        <+12>:  sub    al,BYTE PTR [ebp+0xe]
        <+15>:  add    ah,BYTE PTR [ebp+0xf]
        <+18>:  xor    ax,WORD PTR [ebp+0x12]
        <+22>:  nop
        <+23>:  pop    ebp
        <+24>:  ret 
-----------------------------------------------------------------
start:
	push 0xe54409d5
	push 0xe6cf51f0
	push 0xd2c26416
	call asm3

asm3:
        push   ebp
        mov    ebp,esp
        xor    eax,eax
        mov    ah,BYTE PTR [ebp+0x9]
        shl    ax,0x10
        sub    al,BYTE PTR [ebp+0xe]
        add    ah,BYTE PTR [ebp+0xf]
        xor    ax,WORD PTR [ebp+0x12]
        nop
        pop    ebp
        ret   
```
## Bandera
```
ox375
```