## Objetivo
What can you do with this file? I forgot the key to my safe but this [file](https://artifacts.picoctf.net/c/288/SafeOpener.class) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?
## Solución
En este reto descargamos el archivo y nos vamos al link que puse en "Referencias" abrimos el archivo y le damos donde dice decompiler y nos da el codigo  y ahí buscamos un string con la bandera.
```
(kali㉿kali)-[~/Documents/reverse3]
└─$ wget https://artifacts.picoctf.net/c/288/SafeOpener.class
--2023-11-14 15:03:36--  https://artifacts.picoctf.net/c/288/SafeOpener.class
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.64, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2036 (2.0K) [application/octet-stream]
Saving to: ‘SafeOpener.class’

SafeOpener.class                                           100%[=======================================================================================================================================>]   1.99K  --.-KB/s    in 0s      

2023-11-14 15:03:37 (17.6 MB/s) - ‘SafeOpener.class’ saved [2036/2036]

import java.io.IOException;
import java.util.Base64;
import java.io.Reader;
import java.io.BufferedReader;
import java.io.InputStreamReader;

// // Decompiled by Procyon v0.5.36
// public class SafeOpener
{
    public static void main(final String[] args) throws IOException {
        final BufferedReader keyboard = new BufferedReader(new InputStreamReader(System.in));
        final Base64.Encoder encoder = Base64.getEncoder();
        String encodedkey = "";
        String key = "";
        for (int i = 0; i < 3; ++i) {
            System.out.print("Enter password for the safe: ");
            key = keyboard.readLine();
            encodedkey = encoder.encodeToString(key.getBytes());
            System.out.println(encodedkey);
            final boolean isOpen = openSafe(encodedkey);
            if (isOpen) {
                break;
            }
            System.out.println("You have  " + (2 - i) + " attempt(s) left");
        }
    }
    
    public static boolean openSafe(final String password) {
        final String encodedkey = "picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_5bfbd6f1}";
        if (password.equals(encodedkey)) {
            System.out.println("Sesame open");
            return true;
        }
        System.out.println("Password is incorrect\n");
        return false;
    }
}
```
## Bandera
```
picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_5bfbd6f1}
```
## Referencias
http://www.javadecompilers.com