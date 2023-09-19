## Bandit Level 27 - Level 28

## Objetivo
There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via the port `2220`. The password for the user `bandit27-git` is the same as for the user `bandit27`.
## Datos de acceso al nivel
```
bandit27 YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
```
## Solución
```
bandit27@bandit:~$ mktemp -d
/tmp/tmp.RmlqO5zKzz
bandit27@bandit:~$ git clone ssh://bandit27-
fatal: could not create work tree dir 'bandit27-': Permission denied
bandit27-git/repoba
bandit27@bandit:~$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
fatal: could not create work tree dir 'repo': Permission denied
bandit27@bandit:~$ cd /tmp/tmp.RmlqO5zKzz
bandit27@bandit:/tmp/tmp.RmlqO5zKzz$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit27-git@localhost's password:
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
Receiving objects: 100% (3/3), 286 bytes | 286.00 KiB/s, done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
bandit27@bandit:/tmp/tmp.RmlqO5zKzz$ ls -la
total 124
drwx------  3 bandit27 bandit27   4096 Mar  1 01:59 .
drwxrwx-wt 52 root     root     114688 Mar  1 02:01 ..
drwxrwxr-x  3 bandit27 bandit27   4096 Mar  1 02:00 repo
bandit27@bandit:/tmp/tmp.RmlqO5zKzz$ cd repo/
bandit27@bandit:/tmp/tmp.RmlqO5zKzz/repo$ ls
README
bandit27@bandit:/tmp/tmp.RmlqO5zKzz/repo$ cat README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
bandit27@bandit:/tmp/tmp.RmlqO5zKzz/repo$
```
## Notas adicionales
## Referencias