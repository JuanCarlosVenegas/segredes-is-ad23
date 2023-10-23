## Objetivo
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt) is all blank!
## Solución
```
┌──(kali㉿kali)-[~/hacking/picoCTF-Forensic2]
└─$ wget https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt
--2023-10-22 19:02:59--  https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2964 (2.9K) [application/octet-stream]
Saving to: ‘whitepages.txt’

whitepages.txt               100%[============================================>]   2.89K  --.-KB/s    in 0.001s  

2023-10-22 19:03:08 (4.69 MB/s) - ‘whitepages.txt’ saved [2964/2964]

                                                                                                                  
┌──(kali㉿kali)-[~/hacking/picoCTF-Forensic2]
└─$ cat whitepages.txt
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
┌──(kali㉿kali)-[~/hacking/picoCTF-Forensic2]
└─$ ls -la                 
total 8
drwxrwx--- 1 root vboxsf    0 Oct 22 19:03 .
drwxrwx--- 1 root vboxsf 4096 Oct 22 18:44 ..
drwxrwx--- 1 root vboxsf    0 Oct 22 18:55 m00nwalk
drwxrwx--- 1 root vboxsf    0 Oct 22 19:00 whitepages
-rwxrwx--- 1 root vboxsf 2964 Oct 26  2020 whitepages.txt
                                                                                                                  
┌──(kali㉿kali)-[~/hacking/picoCTF-Forensic2]
└─$ wc whitepages.txt                                                                                 
   0    0 2964 whitepages.txt
                                                                                                                  
┌──(kali㉿kali)-[~/hacking/picoCTF-Forensic2]
└─$ file whitepages.txt 
whitepages.txt: Unicode text, UTF-8 text, with very long lines (1376), with no line terminators
(kali㉿kali)-[~/hacking/picoCTF-Forensic2]
└─$ xxd whitepages.txt | head 
00000000: e280 83e2 8083 e280 83e2 8083 20e2 8083  ............ ...
00000010: 20e2 8083 e280 83e2 8083 e280 83e2 8083   ...............
00000020: 20e2 8083 e280 8320 e280 83e2 8083 e280   ...... ........
00000030: 83e2 8083 20e2 8083 e280 8320 e280 8320  .... ...... ... 
00000040: 2020 e280 83e2 8083 e280 83e2 8083 e280    ..............
00000050: 8320 20e2 8083 20e2 8083 e280 8320 e280  .  ... ...... ..
00000060: 8320 20e2 8083 e280 83e2 8083 2020 e280  .  .........  ..
00000070: 8320 20e2 8083 2020 2020 e280 8320 e280  .  ...    ... ..
00000080: 83e2 8083 e280 83e2 8083 2020 e280 8320  ..........  ... 
00000090: e280 8320 e280 8320 e280 83e2 8083 e280  ... ... ........
                                                                                                                  
┌──(kali㉿kali)-[~/hacking/picoCTF-Forensic2]
└─$ python3 -m pip install pwntools
Defaulting to user installation because normal site-packages is not writeable
DEPRECATION: Loading egg at /usr/local/lib/python3.11/dist-packages/PySoundFile-0.9.0.post1-py3.11.egg is deprecated. pip 23.3 will enforce this behaviour change. A possible replacement is to use pip for package installation..  
DEPRECATION: Loading egg at /usr/local/lib/python3.11/dist-packages/sstv-0.1-py3.11.egg is deprecated. pip 23.3 will enforce this behaviour change. A possible replacement is to use pip for package installation..                 
Collecting pwntools                                                                                               
  Obtaining dependency information for pwntools from https://files.pythonhosted.org/packages/73/d2/b7f119f15731bff576586f5472a23ccdb1d976879971fd0da2234119c65a/pwntools-4.11.0-py2.py3-none-any.whl.metadata
  Downloading pwntools-4.11.0-py2.py3-none-any.whl.metadata (5.3 kB)
Requirement already satisfied: paramiko>=1.15.2 in /usr/lib/python3/dist-packages (from pwntools) (2.12.0)
Requirement already satisfied: mako>=1.0.0 in /usr/lib/python3/dist-packages (from pwntools) (1.2.4.dev0)
Collecting capstone>=3.0.5rc2 (from pwntools)
  Obtaining dependency information for capstone>=3.0.5rc2 from https://files.pythonhosted.org/packages/68/b4/033718dfcd08a0f4a7550ddedd6247ece7685266c3cbc560432bec4ac5e4/capstone-5.0.1-py3-none-manylinux1_x86_64.manylinux_2_5_x86_64.whl.metadata
  Downloading capstone-5.0.1-py3-none-manylinux1_x86_64.manylinux_2_5_x86_64.whl.metadata (3.4 kB)
Collecting ropgadget>=5.3 (from pwntools)
  Obtaining dependency information for ropgadget>=5.3 from https://files.pythonhosted.org/packages/79/b3/196c65ada34d0f2d6500693e0e0a0d6e56d3682372eb06c6c1c8b058becb/ROPGadget-7.4-py3-none-any.whl.metadata
  Downloading ROPGadget-7.4-py3-none-any.whl.metadata (868 bytes)
Requirement already satisfied: pyserial>=2.7 in /usr/lib/python3/dist-packages (from pwntools) (3.5)
Requirement already satisfied: requests>=2.0 in /usr/lib/python3/dist-packages (from pwntools) (2.31.0)
Requirement already satisfied: pip>=6.0.8 in /usr/lib/python3/dist-packages (from pwntools) (23.2)
Requirement already satisfied: pygments>=2.0 in /usr/lib/python3/dist-packages (from pwntools) (2.15.1)
Requirement already satisfied: pysocks in /usr/lib/python3/dist-packages (from pwntools) (1.7.1)
Requirement already satisfied: python-dateutil in /usr/lib/python3/dist-packages (from pwntools) (2.8.2)
Requirement already satisfied: packaging in /usr/lib/python3/dist-packages (from pwntools) (23.1)
Requirement already satisfied: psutil>=3.3.0 in /usr/lib/python3/dist-packages (from pwntools) (5.9.4)
Collecting intervaltree>=3.0 (from pwntools)
  Downloading intervaltree-3.1.0.tar.gz (32 kB)
  Preparing metadata (setup.py) ... done
Requirement already satisfied: sortedcontainers in /usr/lib/python3/dist-packages (from pwntools) (2.4.0)
Collecting unicorn>=1.0.2rc1 (from pwntools)
  Downloading unicorn-2.0.1.post1-py2.py3-none-manylinux1_x86_64.manylinux_2_17_x86_64.manylinux2014_x86_64.whl (16.1 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 16.1/16.1 MB 1.2 MB/s eta 0:00:00
Requirement already satisfied: six>=1.12.0 in /usr/lib/python3/dist-packages (from pwntools) (1.16.0)
Collecting rpyc (from pwntools)
  Downloading rpyc-5.3.1-py3-none-any.whl (74 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 74.0/74.0 kB 1.3 MB/s eta 0:00:00
Collecting colored-traceback (from pwntools)
  Downloading colored-traceback-0.3.0.tar.gz (3.8 kB)
  Preparing metadata (setup.py) ... done
Collecting pyelftools>=0.24 (from pwntools)
  Obtaining dependency information for pyelftools>=0.24 from https://files.pythonhosted.org/packages/33/f9/281a411a5281b674b10830a2f312c64464b49916d097b8919f009de579e0/pyelftools-0.30-py2.py3-none-any.whl.metadata
  Downloading pyelftools-0.30-py2.py3-none-any.whl.metadata (381 bytes)
Collecting plumbum (from rpyc->pwntools)
  Obtaining dependency information for plumbum from https://files.pythonhosted.org/packages/6f/e8/a9a580d1d67825d8bdc16f3993ea58c4066769d5f8ba34caaa69a5344b39/plumbum-1.8.2-py3-none-any.whl.metadata
  Downloading plumbum-1.8.2-py3-none-any.whl.metadata (10 kB)
Downloading pwntools-4.11.0-py2.py3-none-any.whl (11.7 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 11.7/11.7 MB 1.0 MB/s eta 0:00:00
Downloading capstone-5.0.1-py3-none-manylinux1_x86_64.manylinux_2_5_x86_64.whl (2.9 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.9/2.9 MB 1.2 MB/s eta 0:00:00
Downloading pyelftools-0.30-py2.py3-none-any.whl (177 kB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 177.6/177.6 kB 323.0 kB/s eta 0:00:00
Downloading ROPGadget-7.4-py3-none-any.whl (32 kB)
Downloading plumbum-1.8.2-py3-none-any.whl (127 kB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 127.0/127.0 kB 1.0 MB/s eta 0:00:00
Building wheels for collected packages: intervaltree, colored-traceback
  Building wheel for intervaltree (setup.py) ... done
  Created wheel for intervaltree: filename=intervaltree-3.1.0-py2.py3-none-any.whl size=26098 sha256=5fc7cee9746edc623a23d59a43de9b9d284387dd4acae7a42a07f3428b3f436e
  Stored in directory: /home/kali/.cache/pip/wheels/31/d7/d9/eec6891f78cac19a693bd40ecb8365d2f4613318c145ec9816
  Building wheel for colored-traceback (setup.py) ... done
  Created wheel for colored-traceback: filename=colored_traceback-0.3.0-py3-none-any.whl size=4607 sha256=0adfa64784f3b857abfdef3d8a866820a5236e0b1f52bd8ffb4167b259d439c0
  Stored in directory: /home/kali/.cache/pip/wheels/45/a9/5f/635d7d8d70eb182fd22f2b0bebce713206e172769bea9f106a
Successfully built intervaltree colored-traceback
Installing collected packages: unicorn, pyelftools, plumbum, intervaltree, colored-traceback, capstone, rpyc, ropgadget, pwntools
  WARNING: The scripts rpyc_classic, rpyc_classic.py, rpyc_registry and rpyc_registry.py are installed in '/home/kali/.local/bin' which is not on PATH.                                                                             
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.                                                                                                                 
  WARNING: The scripts asm, checksec, common, constgrep, cyclic, debug, disablenx, disasm, elfdiff, elfpatch, errno, hex, libcdb, main, phd, pwn, pwnstrip, scramble, shellcraft, template, unhex, update and version are installed in '/home/kali/.local/bin' which is not on PATH.                                                                  
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.                                                                                                                 
Successfully installed capstone-5.0.1 colored-traceback-0.3.0 intervaltree-3.1.0 plumbum-1.8.2 pwntools-4.11.0 pyelftools-0.30 ropgadget-7.4 rpyc-5.3.1 unicorn-2.0.1.post1
(kali㉿kali)-[~/hacking/picoCTF-Forensic2]
└─$ nano exp.py

	from pwn import *

	file = open('whitepages.txt', 'rb')
	data = bytearray(file.read())
	data = data.replace(b'\xe2\x80\x83', b'0')
	data = data.replace(b'\x20', b'1')
	data = data.decode('ascii')
	data = unbits(data)
	
	print(data)

(kali㉿kali)-[~/hacking/picoCTF-Forensic2]
└─$ python exp.py
b'\n\t\tpicoCTF\n\n\t\tSEE PUBLIC RECORDS & BACKGROUND REPORT\n\t\t5000 Forbes Ave, Pittsburgh, PA 15213\n\t\tpicoCTF{not_all_spaces_are_created_equal_c54f27cd05c2189f8147cc6f5deb2e56}\n\t\t'




```
## Bandera
```
picoCTF{not_all_spaces_are_created_equal_c54f27cd05c2189f8147cc6f5deb2e56}

```