# Metódy návrhu efektívnych algoritmov

Návrh efektívneho algoritmu tkví v správnej [[#Všeobecné princípy tvorby programov|tvorbe programu]] a výbere [[Údaje a údajové štruktúry|údajových štruktúr]].

## Všeobecné princípy tvorby programov
Jedná sa o **techniky** programovania.
Konkrétne o **volanie procedúr** rôzneho typu.

**Využitie [[Varianty zoznamov#Zásobník|zásobníka]] pri volaní procedúr**:
- uchováva všetky potrebné **údaje**
- **zásobníkový rámec**:
	- aktuálne parametre
	- lokálne premenné
	- návratová adresa
	- výsledok funkcie
- každé volanie procedúry znamená rámec v zásobníku
- rozlišujeme volajúcu a volanú procedúru

**Činnosti spojené s volaním procedúry (A volá B)**:
- vytvorenie rámca na vrchole zásobníka
- odovzdanie riadenia činnosti procedúre B
- po ukončení B, odovzdáva sa A

### Rekurzia
- Nevedie automaticky k zníženiu zložitosti (zvykne sa kombinovať s ostatnými technikami)
- ide o procedúru, ktorá volá sama seba
- zvykne aj skracovať zápis programu

### Dekompozícia (rozdeľ a panuj)
Spočíva v rozdelení problému na menšie časti a ich riešenia.

Skombinovaním podriešení dostávame riešenie.

Často sa spája s [[#Rekurzia|rekurziou]] na vytvorenie účinnej techniky.

Počet podproblémov ->; Rozmer podproblémov \\\/ |2|3|4|8|9|16
--|--|--|--|--|--|--
$n/2$|$n*log(n)$|$n^{log(3)}$|$n^2$|$n^3$|x|x
$n/4$|x|x|$n*log(n)$|$n^{3/2}$|$n^{log(3)}$|$n^2$
$n/8$|x|x|x|$n*log(n)$|$n^{2/3 * log(3)}$|$n^{4/3}$

### Vyvažovanie
(Balancing)
Efektívne algoritmy vyvažujúce [[#Dekompozícia rozdeľ a panuj|dekompozíciu]] majú spravidla **vyvážené** rozmery podproblémov.

Napr. -> *[[Triedenie#Mergesort|Mergesort]]*
- rozdelíme postupnosť na 2 časti rovnakého rozmeru
- zvlášť usporiadáme obe časti
- počet porovnaní (zložitosť Sort): $T(n) = O_c(n*log(n))$
- zložitosť Merge: $O(n)$

### Dynamické programovanie
(Tabuľková) technika *dynamického programovania* slúži na:
- výpočet riešení všetkých [[#Dekompozícia rozdeľ a panuj|podproblémov]]
- najprv sa riešia podproblémy malého rozmeru, potom veľkého
- uchovanie riešenia

Dve hlavné vlastnosti problému vhodné na riešenie dynamickým programovaním:
- prekrývajúce sa podroblémy
	- opakovane sa vyžadované riešenia rovnakých podproblémov
- optimálna podštruktúra
	- optimálne riešenie problému  možno získať použitím optimálnych riešení podproblémov

Napr. Výpočet Fibonacciho čísel
- zložitosť:
	- použitím [[#Rekurzia|rekurzie]] -> $T(n)=O(1.618^n)$
	- použitím *dynamického prog.* -> $T(n)=O(n)$ $S(n)=O(1)\ /=O(n)$


### Ďalšie
- **Greedy**
	- "lokálne" optimálne rozhodnutie čo má vplyv na optimálnosť celkového riešenia problému
