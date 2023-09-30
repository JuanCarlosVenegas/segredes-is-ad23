## Objetivo
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/a00f554b16385d9970dae424f66ee1ab/warm) has extraordinarily helpful information...
## Solución
```
charlyvr-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/a00f554b16385d9970dae424f66ee1ab/warm
--2023-09-25 16:40:45--  https://mercury.picoctf.net/static/a00f554b16385d9970dae424f66ee1ab/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm'

warm                                           100%[====================================================================================================>]  10.68K  --.-KB/s    in 0s      

2023-09-25 16:40:45 (164 MB/s) - 'warm' saved [10936/10936]

charlyvr-picoctf@webshell:~$ ls -la
total 44
drwxr-xr-x 2 charlyvr-picoctf charlyvr-picoctf   138 Sep 25 16:40 .
drwxr-xr-x 3 root             root                30 Sep 25 16:31 ..
-rw------- 1 charlyvr-picoctf charlyvr-picoctf    97 Sep 25 16:39 .bash_history
-rw-r--r-- 1 charlyvr-picoctf charlyvr-picoctf   220 Sep 25 16:31 .bash_logout
-rw-r--r-- 1 charlyvr-picoctf charlyvr-picoctf  3771 Sep 25 16:31 .bashrc
-rw-r--r-- 1 charlyvr-picoctf charlyvr-picoctf   807 Sep 25 16:31 .profile
-rw-rw-r-- 1 charlyvr-picoctf charlyvr-picoctf   167 Sep 25 16:35 .wget-hsts
-rw-r--r-- 1 root             root              4443 Sep 25 16:40 README.txt
-rw-rw-r-- 1 charlyvr-picoctf charlyvr-picoctf    34 Mar 16  2021 flag
-rw-rw-r-- 1 charlyvr-picoctf charlyvr-picoctf 10936 Mar 16  2021 warm
charlyvr-picoctf@webshell:~$ ./warm
-bash: ./warm: Permission denied
charlyvr-picoctf@webshell:~$ chmod +x warm
charlyvr-picoctf@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!
charlyvr-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_18788aaa}
charlyvr-picoctf@webshell:~$ 
```

## Notas adicionales
## Referencias