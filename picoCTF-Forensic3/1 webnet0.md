## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.
## Solución
``` 
(kali㉿kali)-[~/Documents/pico-3]
└─$ wget https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap   
--2023-10-23 00:54:03--  https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 13163 (13K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                  100%[=================================================>]  12.85K  --.-KB/s    in 0s      

2023-10-23 00:54:15 (262 MB/s) - ‘capture.pcap’ saved [13163/13163]

                                                                                                                        
┌──(kali㉿kali)-[~/Documents/pico-3]
└─$ wget https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key   
--2023-10-23 00:54:35--  https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key                  100%[=================================================>]   1.66K  --.-KB/s    in 0s      

2023-10-23 00:54:44 (66.8 MB/s) - ‘picopico.key’ saved [1704/1704]

(kali㉿kali)-[~/Documents/pico-3]
└─$ file capture.pcap
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 65535)
                                                                                                                        
┌──(kali㉿kali)-[~/Documents/pico-3]
└─$ cat capture.pcap  
(kali㉿kali)-[~/Documents/pico-3]
└─$ wireshark capture.pcap    


```
## Bandera 
``` 
picoCTF{nongshim.shrimp.crackers}
```