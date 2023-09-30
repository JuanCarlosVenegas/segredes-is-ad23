## Objetivo
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `abcba9f7`

Additional details will be available after launching your challenge instance.

`ssh ctf-player@venus.picoctf.net -p 57961`
## Solución
```
ctf-player@pico-chall$ ls -la
total 16
drwxr-xr-x 1 ctf-player ctf-player 4096 Mar 16  2021 .
drwxr-xr-x 1 ctf-player ctf-player 4096 Sep 25 17:33 ..
-rw-r--r-- 1 ctf-player ctf-player   14 Mar 16  2021 1of3.flag.txt
-rw-r--r-- 1 ctf-player ctf-player   56 Mar 16  2021 instructions-to-2of3.txt
ctf-player@pico-chall$ cat 1of3.flag.txt
picoCTF{xxsh_
ctf-player@pico-chall$ cat instructions-to-2of3.txt 
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ cd
ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
ctf-player@pico-chall$ cat instructions-to-2of3.txt 
cat: instructions-to-2of3.txt: No such file or directory
ctf-player@pico-chall$ cd /                         
ctf-player@pico-chall$ cat 
.dockerenv                dev/                      lib/                      opt/                      sbin/                     usr/                      
2of3.flag.txt             etc/                      lib64/                    proc/                     srv/                      var/                      
bin/                      home/                     media/                    root/                     sys/                      
boot/                     instructions-to-3of3.txt  mnt/                      run/                      tmp/                      
ctf-player@pico-chall$ cat 2of3.flag.txt 
0ut_0f_\/\/4t3r_
ctf-player@pico-chall$ cat instructions-to-3of3.txt 
Lastly, ctf-player, go home... more succinctly `~`
ctf-player@pico-chall$ cd 
ctf-player@pico-chall$ ls -la  
total 32
drwxr-xr-x 1 ctf-player ctf-player 4096 Sep 25 17:33 .
drwxr-xr-x 1 root       root       4096 Mar 16  2021 ..
drwx------ 2 ctf-player ctf-player 4096 Sep 25 17:33 .cache
-rw-r--r-- 1 ctf-player ctf-player   80 Mar 16  2021 .profile
drw------- 1 ctf-player ctf-player 4096 Mar 16  2021 .ssh
-rw-r--r-- 1 ctf-player ctf-player   10 Mar 16  2021 3of3.flag.txt
drwxr-xr-x 1 ctf-player ctf-player 4096 Mar 16  2021 drop-in
ctf-player@pico-chall$ cat +
cat: +: No such file or directory
ctf-player@pico-chall$ cat ~
cat: /home/ctf-player: Is a directory
ctf-player@pico-chall$ cat 3of3.flag.txt 
21cac893}
ctf-player@pico-chall$ Connection to venus.picoctf.net closed by remote host.
Connection to venus.picoctf.net closed.
charlyvr-picoctf@webshell:~$ 

picoCTF{xxsh_0ut_0f_\/\/4t3r_21cac893}
```
