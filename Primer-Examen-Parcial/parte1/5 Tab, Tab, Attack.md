## Objetivo
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/3afd18a65e42b80526aa87f9766c588b/Addadshashanammu.zip)
## Solución
```
charlyvr-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/3afd18a65e42b80526aa87f9766c588b/Addadshashanammu.zip
--2023-09-25 17:22:39--  https://mercury.picoctf.net/static/3afd18a65e42b80526aa87f9766c588b/Addadshashanammu.zip
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4520 (4.4K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip                           100%[====================================================================================================>]   4.41K  --.-KB/s    in 0s      

2023-09-25 17:22:39 (2.19 GB/s) - 'Addadshashanammu.zip' saved [4520/4520]

charlyvr-picoctf@webshell:~$ ls -la
total 28
drwxr-xr-x 2 charlyvr-picoctf charlyvr-picoctf  124 Sep 25 17:22 .
drwxr-xr-x 3 root             root               30 Sep 25 16:31 ..
-rw------- 1 charlyvr-picoctf charlyvr-picoctf   97 Sep 25 16:39 .bash_history
-rw-r--r-- 1 charlyvr-picoctf charlyvr-picoctf  220 Sep 25 16:31 .bash_logout
-rw-r--r-- 1 charlyvr-picoctf charlyvr-picoctf 3771 Sep 25 16:31 .bashrc
-rw-r--r-- 1 charlyvr-picoctf charlyvr-picoctf  807 Sep 25 16:31 .profile
-rw-rw-r-- 1 charlyvr-picoctf charlyvr-picoctf  167 Sep 25 16:35 .wget-hsts
-rw-rw-r-- 1 charlyvr-picoctf charlyvr-picoctf 4520 Mar 16  2021 Addadshashanammu.zip
charlyvr-picoctf@webshell:~$ unzip Addadshashanammu.zip
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
charlyvr-picoctf@webshell:~$ ls -la
total 28
drwxr-xr-x 3 charlyvr-picoctf charlyvr-picoctf  148 Sep 25 17:23 .
drwxr-xr-x 3 root             root               30 Sep 25 16:31 ..
-rw------- 1 charlyvr-picoctf charlyvr-picoctf   97 Sep 25 16:39 .bash_history
-rw-r--r-- 1 charlyvr-picoctf charlyvr-picoctf  220 Sep 25 16:31 .bash_logout
-rw-r--r-- 1 charlyvr-picoctf charlyvr-picoctf 3771 Sep 25 16:31 .bashrc
-rw-r--r-- 1 charlyvr-picoctf charlyvr-picoctf  807 Sep 25 16:31 .profile
-rw-rw-r-- 1 charlyvr-picoctf charlyvr-picoctf  167 Sep 25 16:35 .wget-hsts
drwxr-xr-x 3 charlyvr-picoctf charlyvr-picoctf   28 Mar 16  2021 Addadshashanammu
-rw-rw-r-- 1 charlyvr-picoctf charlyvr-picoctf 4520 Mar 16  2021 Addadshashanammu.zip
charlyvr-picoctf@webshell:~$ cd Addadshashanammu/Almurbalarammi//Ashalmimilkala//Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
charlyvr-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet
charlyvr-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls -la
total 12
drwxr-xr-x 2 charlyvr-picoctf charlyvr-picoctf   35 Mar 16  2021 .
drwxr-xr-x 3 charlyvr-picoctf charlyvr-picoctf   27 Mar 16  2021 ..
-rwxr-xr-x 1 charlyvr-picoctf charlyvr-picoctf 8320 Mar 16  2021 fang-of-haynekhtnamet
charlyvr-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ./fang-of-haynekhtnamet
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_d32e018c}
charlyvr-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ 
```