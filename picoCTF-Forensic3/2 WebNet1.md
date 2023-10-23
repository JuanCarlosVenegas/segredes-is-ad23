## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.
## Solución
``` 
(kali㉿kali)-[~/Documents/pico-3/webnet1]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
--2023-10-23 01:19:17--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 92525 (90K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                 100%[============================================>]  90.36K  --.-KB/s    in 0.1s    

2023-10-23 01:19:26 (717 KB/s) - ‘capture.pcap’ saved [92525/92525]

                                                                                                                  
┌──(kali㉿kali)-[~/Documents/pico-3/webnet1]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key   
--2023-10-23 01:20:07--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key                 100%[============================================>]   1.66K  --.-KB/s    in 0s      

2023-10-23 01:20:15 (45.2 MB/s) - ‘picopico.key’ saved [1704/1704]

(kali㉿kali)-[~/Documents/pico-3/webnet1]
└─$ open vulture.jpg 
──(kali㉿kali)-[~/Documents/pico-3/webnet1]
└─$ strings vulture.jpg -n15 
picoCTF{honey.roasted.peanuts}
 )/'%'/9339GDG]]}
 )/'%'/9339GDG]]}
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz

```
## Bandera 
``` 
picoCTF{honey.roasted.peanuts}
```