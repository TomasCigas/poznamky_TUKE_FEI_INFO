# Analýza algoritmov

Analýza algoritmov je **predikcia** fungovania algoritmu, teda akým spôsobom bude využívať zdroje, koľko času zaberie a pod.

**Inštancia problému** -> vstup, pre ktorý potrebujeme nájsť riešenie

Algoritmy pre riešenie rovnakého problému sa môžu líšiť v **efektívnosti** -> využívanie zdrojov.

Vstup do algoritmu predstavuje premenná $n$. Napr. v prípade triedenia je $n$ vstupná postupnosť.

Pri analýze algortimov využívame niekedy aj pokročilejšie techniky ako napr. *agregačná metóda* (zlučovanie operácií do väčších celkov), čo vyúsťuje do *amortizovanej* časovej zložitosti. 
Teda jednoducho povedané: v algoritme môže nastávať vzácne jeden najhorší prípad, čo znižuje presnosť analýzy, tak analyzujeme skupinu, či celok príkazov.

## Zložitosť
Miera zložitosti môže byť:
**Časová** -> napr. čas na vykonanie 1 inštrukcie
**Priestorová** -> napr. využitie registrov

**Najhoršia** -> maximálna zložitosť všetkých vstupov
**Priemerná**

### Asymptotická notácia
Zjednodušenie vyjadreni zložitosti je **Asymptotická notácia** $O(f(n))$(*Big O complexity*):
- dosahovaná ako limitná so vzrastujúcim $n$
- stupeň rastu funkcie
- Asymptotické ohraničenie zhora (pokiaľ ide o $\ohm$, tak zdola, resp. $\theta$ -> zhora aj zdola)
- **Definícia**: $T(n) = O(f(n))$, ak pre každé $n$ s výnimkou konečného počtu prípadov existuje $c: T(n) \leq c*f(n)$. ($T(n)$ je rádu $f(n)).

Pracujeme s abstrakciou počítača, predikcia doby behu algoritmu sa môže líšiť o konštantný faktor.

## Cenové kritériá
Bez ohľadu na čas alebo pamäť
**Uniformné** -> každá inštrukcia zaberá rovnaký čas a zdroje
**Logaritmické** -> cena závisí od rozmeru povahy operandu 
![[log_price_function.excalidraw]]

Primárnym kritériom (časovej) efektívnosti algoritmu pracujúceho so súbormi je **čítanie/zapisovanie blokov** dát.


