# Zväzy
**Zväzy** sú [[Čiastočne usporiadané množiny|ČUM]], v ktorej každé dva prvky majú spojenie a priesek.
Nech $(A;\preceq)\ x,y\ \epsilon A$

**Spojenie** je $inf\{x,y\}$ = $x \wedge y$
**Priesek** je $sup\{x,y\}$ = $x \vee y$

Pozri [[Čiastočne usporiadané množiny#Ohraničenia|inf a sup]].

Vo zväze môžeme chápať priesek a spojenie ako zobrazenia: 
$$
\wedge : A\times A\rightarrow A
$$
**binárne operácie**

## Komplement
Pre zväz $L$ nazývame prvok $x'\ \epsilon\ L$ **komplementom** k prvku $x\ \epsilon\ L$ práve vtedy ak:
$$
x \wedge x' = O\ a\ x \vee x' = I
$$
Kde $O = inf(L)$ a $I = sup(L)$

## Vlastnosti zväzov
Ak máme zväz $L$ tak je:
### Komplementárny
Keď každý prvok $x\ \epsilon\ L$ má svoj komplement $x'\ \epsilon\ L$

### Distributívny
Ak pre všetky $x,y,z\ \epsilon\ L$ platí:
$$
x\ \wedge(y\vee z) = (x\wedge y)\vee (x\wedge z),
$$
$$
x\ \vee(y\wedge z) = (x\vee y)\wedge (x\vee z)
$$

Zväzy $N_5$ a $M_5$ nie sú distributívne, lebo v oboch sa dá nájsť trojica prvkov, pre ktoré neplatí aspoň jedna z rovností. Ich [[Čiastočne usporiadané množiny#Hasseho diagram|Hasseho diagramy]]:
![[N5aM5.png]]


Z toho nám vyplíva, že všetky zväzy obsahujúce [[#Podzväz|podzväz]] sú [[#Homomorfizmus|izomorfné]] s $N_5$ alebo $M_5$ tiež nebude distributívny.

### Boolovský
ak je komplementárny a distributívny.

#### Tvrdenia
1. V boolovskom zväze $(L,\wedge,\vee)$ má každý prvok práve jeden komplement.
_doplň dôkaz_

2. V každom boolovskom zväze platí:
$$
(a')' = a
$$
$$
(a\vee b)' = a'\wedge b',\ (a\wedge b)' = a'\vee b'
$$
$$
(de\ Morgan\ pravidlá)
$$


## Podzväz
Zväz $(L',\wedge,\vee)$ je podzväz zväzu $(L,\wedge,\vee)$, ak $L'\leqq L$ a pre $\forall x,y\ \epsilon\ L$:
$$
x\wedge y = x\ \wedge y
x\vee y = x\ \vee y
$$
Teda výsledok [[Zväzy#Zväzy|prieseku a spojenia]] jednotlivých prvkov v podzväze musí byť rovnaký ako v danom "nadzväze" (pôvodnom zväze).

## Homomorfizmus
**Homomorfizmus** zväzov $L(\wedge,\vee)$,$L'(\wedge,\vee)$ je zobrazenie $L\rightarrow L'$, v ktorom pre $\forall x,y\ \epsilon\ L$ platí:
$$
f(x\wedge y) = f(x)\vee f(y),
f(x\vee y) = f(x) \wedge f(y)
$$

Ak je [[Zobrazenia#Druhy zobrazení|bijekcia]] množiny $L$ na $L'$ vzhľadom na **obidve** operácie je **IZOMORFIZMUS**. Takéto zväzy majú teda rovnaký [[Čiastočne usporiadané množiny#Hasseho diagram|hasseho diagram]]. 
__input file__