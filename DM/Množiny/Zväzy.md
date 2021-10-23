# Zväzy
**Zväzy** sú [[Čiastočne usporiadané množiny|ČUM]], v ktorej každé dva prvky majú spojenie a priesek.
Nech $(A;\preceq)\ x,y\ \epsilon A$

**Spojenie** je $inf\{x,y\}$
**Priesek** je $sup\{x,y\}$

Pozri [[Čiastočne usporiadané množiny#Ohraničenia|inf a sup]].

## Komplement
Prvok $x'\ \epsilon\ L$ nazývame **komplementom** k prvku $x$ práve vtedy ak:
$$
x\ \wedge\ x' = O\ a\ x\ \vee\ x' = I
$$
Kde $O = inf(L)$ a $I = sup(L)$

## Vlastnosti zväzov
Ak máme zväz $L$
1. Je **komplementárny**, keď každý prvok $x\ \epsilon\ L$ má svoj komplement $x'\ \epsilon\ L$
2. Je **distributívny**, ak pre všetky $x,y,z\ \epsilon\ L$ platí:
$$
x\ \wedge(y\vee z) = (x\wedge y)\vee (x\wedge z),
$$
$$
x\ \vee(y\wedge z) = (x\vee y)\wedge (x\vee z)
$$

Zväzy $N_5$ a $M_5$ nie sú distributívne, lebo v oboch sa dá nájsť trojica prvkov, pre ktoré neplatí aspoň jedna z rovností. Ich [[Čiastočne usporiadané množiny#Hasseho diagram|Hasseho diagramy]]:
![[N5aM5.png]]

Z toho nám vyplíva, že všetky zväzy obsahujúce podzväz [[Grupy#Izomorfizmus|imorfný]] s $N_5$ alebo $M_5$ tiež nebude distributívny.