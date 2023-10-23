## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.
## Solución
```
kali㉿kali)-[~/hacking/picoCTF-Forensic2/sharkonwire2]
└─$ wget https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
--2023-10-22 21:52:11--  https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 112318 (110K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                                               100%[=======================================================================================================================================>] 109.69K   455KB/s    in 0.2s    

2023-10-22 21:52:20 (455 KB/s) - ‘capture.pcap’ saved [112318/112318]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/hacking/picoCTF-Forensic2/sharkonwire2]
└─$ file capture.pcap                               
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/hacking/picoCTF-Forensic2/sharkonwire2]
└─$ wireshark capture.pcap    
(kali㉿kali)-[~/hacking/picoCTF-Forensic2/sharkonwire2]
└─$ python3 -m pip install scapy   
Defaulting to user installation because normal site-packages is not writeable
DEPRECATION: Loading egg at /usr/local/lib/python3.11/dist-packages/PySoundFile-0.9.0.post1-py3.11.egg is deprecated. pip 23.3 will enforce this behaviour change. A possible replacement is to use pip for package installation..
DEPRECATION: Loading egg at /usr/local/lib/python3.11/dist-packages/sstv-0.1-py3.11.egg is deprecated. pip 23.3 will enforce this behaviour change. A possible replacement is to use pip for package installation..
Requirement already satisfied: scapy in /usr/lib/python3/dist-packages (2.5.0)

(kali㉿kali)-[~/hacking/picoCTF-Forensic2/sharkonwire2]
└─$ nano exp.py   
                                                                                                                      
┌──(kali㉿kali)-[~/hacking/picoCTF-Forensic2/sharkonwire2]
└─$ python3 exp.py
<capture.pcap: TCP:138 UDP:614 ICMP:0 Other:574>

(kali㉿kali)-[~/hacking/picoCTF-Forensic2/sharkonwire2]
└─$ nano exp.py 
	from scapy.all import *

	packets = rdpcap('capture.pcap')
	
	flag = ''
	
	for p in packets:
	        if UDP in p and p[UDP].dport == 22:
	                if p[UDP].sport > 5000:
	                        flag += chr(p[UDP].sport - 5000)
	print(flag)

─(kali㉿kali)-[~/hacking/picoCTF-Forensic2/sharkonwire2]
└─$ python3 exp.py
picoCTF{p1LLf3r3d_data_v1a_st3g0}


```
## Bandera
```
picoCTF{p1LLf3r3d_data_v1a_st3g0}
```
