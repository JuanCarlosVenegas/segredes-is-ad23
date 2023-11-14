## Objetivo
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this). Can you reverse the flag.
## Solución
' -A50 ahora descargamos la herramienta GHIDRA Y ponemos el archivo binario para hacerle reversing tendremos que modificar los nombres de unas variables para hacer mas entendible el codigo ahora en un archivo de python creamos un pequeño programa para recorrer todo el archivo donde modificamos las variables y una vez que lo hagamos encontraremos la bandera
```
(kali㉿kali)-[~/Documents/reverse3]
└─$ wget https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev       
--2023-11-14 13:48:33--  https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16856 (16K) [application/octet-stream]
Saving to: ‘rev’

rev                          100%[============================================>]  16.46K  --.-KB/s    in 0s      

2023-11-14 13:48:34 (156 MB/s) - ‘rev’ saved [16856/16856]

                                                                                                                  
┌──(kali㉿kali)-[~/Documents/reverse3]
└─$ wget https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this
--2023-11-14 13:48:45--  https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 24 [application/octet-stream]
Saving to: ‘rev_this’

rev_this                     100%[============================================>]      24  --.-KB/s    in 0s      

2023-11-14 13:48:45 (55.4 MB/s) - ‘rev_this’ saved [24/24]

─(kali㉿kali)-[~/Documents/reverse3]
└─$ objdump -D rev intel | grep '<main>' -A50
    10bd:       48 8d 3d c1 00 00 00    lea    0xc1(%rip),%rdi        # 1185 <main>
    10c4:       ff 15 16 2f 00 00       call   *0x2f16(%rip)        # 3fe0 <__libc_start_main@GLIBC_2.2.5>
    10ca:       f4                      hlt
    10cb:       0f 1f 44 00 00          nopl   0x0(%rax,%rax,1)

00000000000010d0 <deregister_tm_clones>:
    10d0:       48 8d 3d 81 2f 00 00    lea    0x2f81(%rip),%rdi        # 4058 <__TMC_END__>
    10d7:       48 8d 05 7a 2f 00 00    lea    0x2f7a(%rip),%rax        # 4058 <__TMC_END__>
    10de:       48 39 f8                cmp    %rdi,%rax
    10e1:       74 15                   je     10f8 <deregister_tm_clones+0x28>
    10e3:       48 8b 05 ee 2e 00 00    mov    0x2eee(%rip),%rax        # 3fd8 <_ITM_deregisterTMCloneTable>
    10ea:       48 85 c0                test   %rax,%rax
    10ed:       74 09                   je     10f8 <deregister_tm_clones+0x28>
    10ef:       ff e0                   jmp    *%rax
    10f1:       0f 1f 80 00 00 00 00    nopl   0x0(%rax)
    10f8:       c3                      ret
    10f9:       0f 1f 80 00 00 00 00    nopl   0x0(%rax)

0000000000001100 <register_tm_clones>:
    1100:       48 8d 3d 51 2f 00 00    lea    0x2f51(%rip),%rdi        # 4058 <__TMC_END__>
    1107:       48 8d 35 4a 2f 00 00    lea    0x2f4a(%rip),%rsi        # 4058 <__TMC_END__>
    110e:       48 29 fe                sub    %rdi,%rsi
    1111:       48 c1 fe 03             sar    $0x3,%rsi
    1115:       48 89 f0                mov    %rsi,%rax
    1118:       48 c1 e8 3f             shr    $0x3f,%rax
    111c:       48 01 c6                add    %rax,%rsi
    111f:       48 d1 fe                sar    %rsi
    1122:       74 14                   je     1138 <register_tm_clones+0x38>
    1124:       48 8b 05 c5 2e 00 00    mov    0x2ec5(%rip),%rax        # 3ff0 <_ITM_registerTMCloneTable>
    112b:       48 85 c0                test   %rax,%rax
    112e:       74 08                   je     1138 <register_tm_clones+0x38>
    1130:       ff e0                   jmp    *%rax
    1132:       66 0f 1f 44 00 00       nopw   0x0(%rax,%rax,1)
    1138:       c3                      ret
    1139:       0f 1f 80 00 00 00 00    nopl   0x0(%rax)

0000000000001140 <__do_global_dtors_aux>:
    1140:       80 3d 11 2f 00 00 00    cmpb   $0x0,0x2f11(%rip)        # 4058 <__TMC_END__>
    1147:       75 2f                   jne    1178 <__do_global_dtors_aux+0x38>
    1149:       55                      push   %rbp
    114a:       48 83 3d a6 2e 00 00    cmpq   $0x0,0x2ea6(%rip)        # 3ff8 <__cxa_finalize@GLIBC_2.2.5>
    1151:       00 
    1152:       48 89 e5                mov    %rsp,%rbp
    1155:       74 0c                   je     1163 <__do_global_dtors_aux+0x23>
    1157:       48 8b 3d f2 2e 00 00    mov    0x2ef2(%rip),%rdi        # 4050 <__dso_handle>
    115e:       e8 2d ff ff ff          call   1090 <__cxa_finalize@plt>
    1163:       e8 68 ff ff ff          call   10d0 <deregister_tm_clones>
    1168:       c6 05 e9 2e 00 00 01    movb   $0x1,0x2ee9(%rip)        # 4058 <__TMC_END__>
    116f:       5d                      pop    %rbp
    1170:       c3                      ret
    1171:       0f 1f 80 00 00 00 00    nopl   0x0(%rax)
--
0000000000001185 <main>:
    1185:       55                      push   %rbp
    1186:       48 89 e5                mov    %rsp,%rbp
    1189:       48 83 ec 50             sub    $0x50,%rsp
    118d:       48 8d 35 74 0e 00 00    lea    0xe74(%rip),%rsi        # 2008 <_IO_stdin_used+0x8>
    1194:       48 8d 3d 6f 0e 00 00    lea    0xe6f(%rip),%rdi        # 200a <_IO_stdin_used+0xa>
    119b:       e8 d0 fe ff ff          call   1070 <fopen@plt>
    11a0:       48 89 45 e8             mov    %rax,-0x18(%rbp)
    11a4:       48 8d 35 68 0e 00 00    lea    0xe68(%rip),%rsi        # 2013 <_IO_stdin_used+0x13>
    11ab:       48 8d 3d 63 0e 00 00    lea    0xe63(%rip),%rdi        # 2015 <_IO_stdin_used+0x15>
    11b2:       e8 b9 fe ff ff          call   1070 <fopen@plt>
    11b7:       48 89 45 e0             mov    %rax,-0x20(%rbp)
    11bb:       48 83 7d e8 00          cmpq   $0x0,-0x18(%rbp)
    11c0:       75 0c                   jne    11ce <main+0x49>
    11c2:       48 8d 3d 57 0e 00 00    lea    0xe57(%rip),%rdi        # 2020 <_IO_stdin_used+0x20>
    11c9:       e8 62 fe ff ff          call   1030 <puts@plt>
    11ce:       48 83 7d e0 00          cmpq   $0x0,-0x20(%rbp)
    11d3:       75 0c                   jne    11e1 <main+0x5c>
    11d5:       48 8d 3d 7e 0e 00 00    lea    0xe7e(%rip),%rdi        # 205a <_IO_stdin_used+0x5a>
    11dc:       e8 4f fe ff ff          call   1030 <puts@plt>
    11e1:       48 8b 55 e8             mov    -0x18(%rbp),%rdx
    11e5:       48 8d 45 b0             lea    -0x50(%rbp),%rax
    11e9:       48 89 d1                mov    %rdx,%rcx
    11ec:       ba 01 00 00 00          mov    $0x1,%edx
    11f1:       be 18 00 00 00          mov    $0x18,%esi
    11f6:       48 89 c7                mov    %rax,%rdi
    11f9:       e8 42 fe ff ff          call   1040 <fread@plt>
    11fe:       89 45 dc                mov    %eax,-0x24(%rbp)
    1201:       83 7d dc 00             cmpl   $0x0,-0x24(%rbp)
    1205:       7f 0a                   jg     1211 <main+0x8c>
    1207:       bf 00 00 00 00          mov    $0x0,%edi
    120c:       e8 6f fe ff ff          call   1080 <exit@plt>
    1211:       c7 45 f8 00 00 00 00    movl   $0x0,-0x8(%rbp)
    1218:       eb 23                   jmp    123d <main+0xb8>
    121a:       8b 45 f8                mov    -0x8(%rbp),%eax
    121d:       48 98                   cltq
    121f:       0f b6 44 05 b0          movzbl -0x50(%rbp,%rax,1),%eax
    1224:       88 45 ff                mov    %al,-0x1(%rbp)
    1227:       0f be 45 ff             movsbl -0x1(%rbp),%eax
    122b:       48 8b 55 e0             mov    -0x20(%rbp),%rdx
    122f:       48 89 d6                mov    %rdx,%rsi
    1232:       89 c7                   mov    %eax,%edi
    1234:       e8 27 fe ff ff          call   1060 <fputc@plt>
    1239:       83 45 f8 01             addl   $0x1,-0x8(%rbp)
    123d:       83 7d f8 07             cmpl   $0x7,-0x8(%rbp)
    1241:       7e d7                   jle    121a <main+0x95>
    1243:       c7 45 f4 08 00 00 00    movl   $0x8,-0xc(%rbp)
    124a:       eb 43                   jmp    128f <main+0x10a>
    124c:       8b 45 f4                mov    -0xc(%rbp),%eax
    124f:       48 98                   cltq
    1251:       0f b6 44 05 b0          movzbl -0x50(%rbp,%rax,1),%eax
objdump: 'intel': No such file

```
## Bandera
```
picoCTF{r3v3rs37ee84d27}
```