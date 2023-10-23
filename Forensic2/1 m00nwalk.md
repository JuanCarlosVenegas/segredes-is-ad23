## Objetivo
Decode this [message](https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav) from the moon.
## Solución
```
─(kali㉿kali)-[~/hacking/picoCTF-Forensic2]
└─$ cd m00nwalk         
                                                                                                                  
┌──(kali㉿kali)-[~/hacking/picoCTF-Forensic2/m00nwalk]
└─$ wget https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav   
--2023-10-22 16:52:00--  https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 11066998 (11M) [application/octet-stream]
Saving to: ‘message.wav’

message.wav                                                100%[========================================================================================================================================>]  10.55M   628KB/s    in 13s     

2023-10-22 16:52:22 (820 KB/s) - ‘message.wav’ saved [11066998/11066998]

                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/hacking/picoCTF-Forensic2/m00nwalk]
└─$ file message.wav 
message.wav: RIFF (little-endian) data, WAVE audio, Microsoft PCM, 16 bit, mono 48000 Hz
                                                                                                                  
┌──(kali㉿kali)-[~/hacking/picoCTF-Forensic2/m00nwalk]
└─$ open message.wav 
(kali㉿kali)-[~]
└─$ cd /opt
                                                                                                                  
┌──(kali㉿kali)-[/opt]
└─$ sudo git clone https://github.com/colaclanth/sstv.git
[sudo] password for kali: 
Cloning into 'sstv'...
remote: Enumerating objects: 221, done.
remote: Counting objects: 100% (59/59), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 221 (delta 51), reused 49 (delta 49), pack-reused 162
Receiving objects: 100% (221/221), 1.01 MiB | 871.00 KiB/s, done.
Resolving deltas: 100% (139/139), done.
                                                                                                                  
┌──(kali㉿kali)-[/opt]
└─$ cd sstv                                              
                                                                                                                  
┌──(kali㉿kali)-[/opt/sstv]
└─$ sudo python3 setup.py install                        
running install
/usr/lib/python3/dist-packages/setuptools/_distutils/cmd.py:66: SetuptoolsDeprecationWarning: setup.py install is deprecated.
!!

        ********************************************************************************
        Please avoid running ``setup.py`` directly.
        Instead, use pypa/build, pypa/installer, pypa/build or
        other standards-based tools.

        See https://blog.ganssle.io/articles/2021/10/setup-py-deprecated.html for details.
        ********************************************************************************

!!
  self.initialize_options()
/usr/lib/python3/dist-packages/setuptools/_distutils/cmd.py:66: EasyInstallDeprecationWarning: easy_install command is deprecated.
!!

        ********************************************************************************
        Please avoid running ``setup.py`` and ``easy_install``.
        Instead, use pypa/build, pypa/installer, pypa/build or
        other standards-based tools.

        See https://github.com/pypa/setuptools/issues/917 for details.
        ********************************************************************************

!!
  self.initialize_options()
running bdist_egg
running egg_info
creating sstv.egg-info
writing sstv.egg-info/PKG-INFO
writing dependency_links to sstv.egg-info/dependency_links.txt
writing entry points to sstv.egg-info/entry_points.txt
writing requirements to sstv.egg-info/requires.txt
writing top-level names to sstv.egg-info/top_level.txt
writing manifest file 'sstv.egg-info/SOURCES.txt'
reading manifest file 'sstv.egg-info/SOURCES.txt'
adding license file 'LICENSE'
writing manifest file 'sstv.egg-info/SOURCES.txt'
installing library code to build/bdist.linux-x86_64/egg
running install_lib
running build_py
creating build
creating build/lib
creating build/lib/sstv
copying sstv/command.py -> build/lib/sstv
copying sstv/spec.py -> build/lib/sstv
copying sstv/common.py -> build/lib/sstv
copying sstv/__main__.py -> build/lib/sstv
copying sstv/__init__.py -> build/lib/sstv
copying sstv/decode.py -> build/lib/sstv
creating build/bdist.linux-x86_64
creating build/bdist.linux-x86_64/egg
creating build/bdist.linux-x86_64/egg/sstv
copying build/lib/sstv/command.py -> build/bdist.linux-x86_64/egg/sstv
copying build/lib/sstv/spec.py -> build/bdist.linux-x86_64/egg/sstv
copying build/lib/sstv/common.py -> build/bdist.linux-x86_64/egg/sstv
copying build/lib/sstv/__main__.py -> build/bdist.linux-x86_64/egg/sstv
copying build/lib/sstv/__init__.py -> build/bdist.linux-x86_64/egg/sstv
copying build/lib/sstv/decode.py -> build/bdist.linux-x86_64/egg/sstv
byte-compiling build/bdist.linux-x86_64/egg/sstv/command.py to command.cpython-311.pyc
byte-compiling build/bdist.linux-x86_64/egg/sstv/spec.py to spec.cpython-311.pyc
byte-compiling build/bdist.linux-x86_64/egg/sstv/common.py to common.cpython-311.pyc
byte-compiling build/bdist.linux-x86_64/egg/sstv/__main__.py to __main__.cpython-311.pyc
byte-compiling build/bdist.linux-x86_64/egg/sstv/__init__.py to __init__.cpython-311.pyc
byte-compiling build/bdist.linux-x86_64/egg/sstv/decode.py to decode.cpython-311.pyc
creating build/bdist.linux-x86_64/egg/EGG-INFO
copying sstv.egg-info/PKG-INFO -> build/bdist.linux-x86_64/egg/EGG-INFO
copying sstv.egg-info/SOURCES.txt -> build/bdist.linux-x86_64/egg/EGG-INFO
copying sstv.egg-info/dependency_links.txt -> build/bdist.linux-x86_64/egg/EGG-INFO
copying sstv.egg-info/entry_points.txt -> build/bdist.linux-x86_64/egg/EGG-INFO
copying sstv.egg-info/requires.txt -> build/bdist.linux-x86_64/egg/EGG-INFO
copying sstv.egg-info/top_level.txt -> build/bdist.linux-x86_64/egg/EGG-INFO
zip_safe flag not set; analyzing archive contents...
creating dist
creating 'dist/sstv-0.1-py3.11.egg' and adding 'build/bdist.linux-x86_64/egg' to it
removing 'build/bdist.linux-x86_64/egg' (and everything under it)
Processing sstv-0.1-py3.11.egg
Removing /usr/local/lib/python3.11/dist-packages/sstv-0.1-py3.11.egg
Copying sstv-0.1-py3.11.egg to /usr/local/lib/python3.11/dist-packages
Adding sstv 0.1 to easy-install.pth file
Installing sstv script to /usr/local/bin

Installed /usr/local/lib/python3.11/dist-packages/sstv-0.1-py3.11.egg
Processing dependencies for sstv==0.1
Searching for scipy==1.10.1
Best match: scipy 1.10.1
Adding scipy 1.10.1 to easy-install.pth file

Using /usr/lib/python3/dist-packages
Searching for numpy==1.24.2
Best match: numpy 1.24.2
Adding numpy 1.24.2 to easy-install.pth file
Installing f2py script to /usr/local/bin
Installing f2py3 script to /usr/local/bin
Installing f2py3.11 script to /usr/local/bin

Using /usr/lib/python3/dist-packages
Searching for PySoundFile==0.9.0.post1
Best match: PySoundFile 0.9.0.post1
Processing PySoundFile-0.9.0.post1-py3.11.egg
Adding PySoundFile 0.9.0.post1 to easy-install.pth file

Using /usr/local/lib/python3.11/dist-packages/PySoundFile-0.9.0.post1-py3.11.egg
Searching for Pillow==10.0.0
Best match: Pillow 10.0.0
Adding Pillow 10.0.0 to easy-install.pth file

Using /usr/lib/python3/dist-packages
Searching for cffi==1.15.1
Best match: cffi 1.15.1
Adding cffi 1.15.1 to easy-install.pth file

Using /usr/lib/python3/dist-packages
Finished processing dependencies for sstv==0.1
                                                                                                                  
┌──(kali㉿kali)-[/opt/sstv]
└─$ sstv                                                 
                                                                                                                  
┌──(kali㉿kali)-[/opt/sstv/sstv]
└─$ cd ../..

┌──(kali㉿kali)-[~/hacking/picoCTF-Forensic2/m00nwalk]
└─$ sstv -d message.wav -o result.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                                                                  
┌──(kali㉿kali)-[~/hacking/picoCTF-Forensic2/m00nwalk]
└─$ ls
'1 m00nwalk.md'   message.wav   result.png
                                                                                                                  
┌──(kali㉿kali)-[~/hacking/picoCTF-Forensic2/m00nwalk]
└─$ open result.png  
                                                                                                                  
┌──(kali㉿kali)-[~/hacking/picoCTF-Forensic2/m00nwalk]
└─$ 

```
## Bandera
```
picoCTF{beep_boop_im_in_space}
```
