## Bandit Level 15 - Level 16

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**
## Datos de acceso al nivel
```
bandit15 
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```
## Solución
```bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 21 22:03:56 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 21 22:03:56 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 21 22:02:56 2023 GMT; NotAfter: Feb 21 22:03:56 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEF3vcjDANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwMjIxMjIwMjU2WhcNMjMwMjIxMjIwMzU2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCg
1elREdWTbtCZNl7KNMjleNrcG71f9lZhjAfM4x+TDwlPpT+Q9O3V6J687fJdMH85
xfUwcZG0XFCeN1nxnmQadGF/ZHEt0laWmCQfo5LogzgGFcaZWC1a6XZ5ZKv7SRDt
tvPK/CTKwOJD5ZJVEXEk9R8YQ/VbKwZMDc43WD/HKypvBv7fZVbJkKYY75LOby86
7gux29Emhntj5pZyYagYbmonnAiw6447bGTC1d6jilGPhXMzckTI57WGeNdp4ppL
3pXSVDLOU2XJ8Um/L2VIgGTsUk5CwrtzVxyt6I5sKavUhsNGlzqvHI/McgbsnHi8
3LDg9k/Co8F21eZFooVlAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBz
lgp6XhMshglRxhxHRg1xHkVYSFSBaS5Adq5OIoE/oetyedTiO2B9MLmNZ9Juu/WK
/+WZFmNdzQ6Iw5ueBz/rmY+DvzTjjd4CPPqeilG5mngceR5nliM9mXkpQlmm3T1a
8JuBrDugrN9BP4IeBTER0pgQcQvsRATrv/SAVFVBhTSvOKFhoYNEdBzaqxclEjD6
bl3UkzNag/S3iLuv24xoQkMmlFC2afaswkG/cQ4p3BuapuZORjbohUOXS24QDl0z
A2RDFNizi42ZVJ8ZW1qbURZ4n/VbIAi7vRHldPKjC8hYAcdvUekB0schBlc1J06Z
phGCgzTVUzJu9yz8uKzO
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 938A16778B2A5840DA572FFF3231339699680CABDF5B12689B077E0A9E9B96A1
    Session-ID-ctx:
    Resumption PSK: ECF6BDE243FE31D65B4FAEC29555C49B098570ACECACF88E0C4D24CFDDAB13BFB1A6E4359EDF1984145E320359405D2F
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - a5 3d 92 1f d1 78 36 48-bb a6 da 4d 19 13 ee a7   .=...x6H...M....
    0010 - a0 02 59 cf 36 90 28 ed-9c 36 1c 44 15 16 4f 52   ..Y.6.(..6.D..OR
    0020 - 61 03 c7 26 9b 26 f6 b5-c6 97 c7 57 f2 80 84 7f   a..&.&.....W....
    0030 - fd 54 84 28 b8 f5 34 e1-63 27 77 6f e5 f3 94 4d   .T.(..4.c'wo...M
    0040 - 63 46 7e 4d cb a2 1e 4b-a4 e7 37 db e8 01 9c 12   cF~M...K..7.....
    0050 - e6 f6 0e 71 15 e7 7c b6-8f a1 11 31 32 c4 96 1a   ...q..|....12...
    0060 - 1b 3c 04 03 54 6e be 41-6b b8 74 53 62 9a dc 2c   .<..Tn.Ak.tSb..,
    0070 - f0 92 56 81 c7 db 19 98-28 44 82 a5 fc bb 2a f6   ..V.....(D....*.
    0080 - 38 50 73 df 4e 01 a5 0a-e4 0f 10 e4 7a ac 98 12   8Ps.N.......z...
    0090 - 43 8a 51 8c 66 76 a5 81-2b ef cf 9a 0e a7 b9 2b   C.Q.fv..+......+
    00a0 - bc e0 90 cc a6 68 2e 55-6a 78 8a 41 9a 44 8a b4   .....h.Ujx.A.D..
    00b0 - 86 ea 0d 89 a9 49 92 a5-f1 23 41 da 4d 44 b1 5a   .....I...#A.MD.Z
    00c0 - cc d9 3c e4 dd b4 6c fd-a8 cf b3 e9 68 5c b2 34   ..<...l.....h\.4

    Start Time: 1677030433
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: DE6ABD4E22A04C1E6F6CB03C0F15A41ED707F930882B28E3D60304ECC7100F69
    Session-ID-ctx:
    Resumption PSK: 0D59D0FA0AA733B1643F6412F85D1EEC5C9364C33568765580F145429A5EC7CB898D405D599FCA8DFA2AD6C398C1B5F3
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - a5 3d 92 1f d1 78 36 48-bb a6 da 4d 19 13 ee a7   .=...x6H...M....
    0010 - 6f 72 fb 8c 0d ac 0c 32-2f a8 30 b3 b2 81 fe 95   or.....2/.0.....
    0020 - 0e 79 ef 9e 2a 6e ed 29-cd 20 5c 7d 02 6e 6e 0c   .y..*n.). \}.nn.
    0030 - f6 93 94 00 47 b9 f5 61-ed 46 05 ca 3f da 11 ab   ....G..a.F..?...
    0040 - 31 8b 3d a3 b4 61 3b 64-df 7d 85 35 34 25 e5 7f   1.=..a;d.}.54%..
    0050 - 48 e8 e5 d0 a0 b6 a7 a8-cf 4e 07 cb 19 b0 a9 5a   H........N.....Z
    0060 - 84 e3 5a 06 1d 0e 89 a6-5a 92 85 a7 34 8c 92 98   ..Z.....Z...4...
    0070 - af 88 ba 00 82 d0 e4 6a-70 0e 36 14 94 32 6b 9c   .......jp.6..2k.
    0080 - 8d 1e 8e e5 f1 6f 40 90-06 d5 c2 59 59 15 66 d2   .....o@....YY.f.
    0090 - ab 1c 4a 5a e1 e8 4a 2b-33 69 ad 47 ce 18 d0 8e   ..JZ..J+3i.G....
    00a0 - 26 b6 3f f4 2e 49 03 d0-41 e6 86 f5 eb f5 fd 3a   &.?..I..A......:
    00b0 - ce 3c 21 98 53 04 50 28-a9 21 00 8f b2 70 e6 b2   .<!.S.P(.!...p..
    00c0 - 64 f7 4c 4b 35 a2 7d ff-43 10 9c 14 2d 5f db f4   d.LK5.}.C...-_..

    Start Time: 1677030433
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit15@bandit:~$
```
## Notas adicionales
## Referencias