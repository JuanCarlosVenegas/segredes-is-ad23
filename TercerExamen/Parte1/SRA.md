## Objetivo
I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...

Additional details will be available after launching your challenge instance.
## Solución
```
(kali㉿kali)-[~/Documents/3erExamen/SRA]
└─$ wget https://artifacts.picoctf.net/c/294/chal.py                                               
--2023-11-14 16:18:47--  https://artifacts.picoctf.net/c/294/chal.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.61, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 630 [application/octet-stream]
Saving to: ‘chal.py’

chal.py                                                    100%[=======================================================================================================================================>]     630  --.-KB/s    in 0s      

2023-11-14 16:18:48 (20.7 MB/s) - ‘chal.py’ saved [630/630]
from Crypto.Util.number import getPrime, inverse, bytes_to_long
from string import ascii_letters, digits
from random import choice

pride = "".join(choice(ascii_letters + digits) for _ in range(16))
gluttony = getPrime(128)
greed = getPrime(128)
lust = gluttony * greed
sloth = 65537
envy = inverse(sloth, (gluttony - 1) * (greed - 1))

anger = pow(bytes_to_long(pride.encode()), sloth, lust)

print(f"{anger = }")
print(f"{envy = }")

print("vainglory?")
vainglory = input("> ").strip()

if vainglory == pride:
    print("Conquered!")
    with open("/challenge/flag.txt") as f:
        print(f.read())
else:
    print("Hubris!")

--------------------------------------------------------------
from pwn import *
import primefac
from itertools import combinations
from Crypto.Util.number import long_to_bytes

function to generate all the sub lists
def sub_lists (l):
    initializing empty list
    comb = []

    #Iterating till length of list
    for i in range(1,len(l)+1):
        Generating sub list
        comb += [list(j) for j in combinations(l, i)]
    Returning list
    return comb

def divisors(phi):
   print("Give me the divisors of ", phi-1)
  ## this is dangerous, but I'm trusting me
   return(eval(input()))

connect to the server
r = remote('saturn.picoctf.net', 59754)
get ciphertext
r.recvuntil("anger =")
ciphertext=int(r.recvline())
get d
r.recvuntil("envy =")
d=int(r.recvline())
print("cipher=",ciphertext)
print("d=",d)
print(r.recvuntil("vainglory?"))
r.recvline()
since d is e^-1 mod (p-1)*(q-1), d*e=k*(p-1)*(q-1)+1
so (p-1)*(q-1)*k = d*e-1
factors=divisors(d*65537)
combos = sub_lists(factors)
primes = set()
try all possible subsets of the list of factors as the factors of (p-1)
for l in combos:
   product = 1
   multiply them together to get p-1
   for k in l:
	      product = product * k
	if the right length and adding 1 yields a prime, then maybe
	   if product.bit_length()==128 and primefac.isprime(product+1):
	      primes.add(product+1)
	print(primes)
	primelist = list(primes)
	try all possible prime pairs
	for p in primelist:
	   for q in primelist:
	      n=p*q
	      decode with this possible n
	      plain = pow(ciphertext,d,n)
	      try:
	         plaintext = long_to_bytes(plain)
	         see if it corresponds to text and if so, try it
	         print(plaintext.decode())
	         r.sendline(plaintext.decode())
	         print(r.recvline())
	         print(r.recvline())
	         print(r.recvline())
	      except:
	         continue
No JALÓ :(

```
## Bandera
```
picoCTF{No_lo_pude_resolver_:'(}
```