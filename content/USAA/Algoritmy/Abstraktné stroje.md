# Abstraktné stroje
Chceme študovať algoritmy spôsobom nezávislým od konkrétneho jazyka či počítača, preto používame **abstraktné stroje**, teda zjednodušenie konkrétnych počítačov. Predpokladáme **neobmedzenú pamäť** a **neobmedzené registre**.

Napríklad: Turingov stroj, [[#Stroj RAM|stroj RAM]], stroj RASP

## Stroj RAM
Ide o model hardvardského počítača
#add_link 

**Konfigurácia**:
- vstupná, výstupná páska, pamäť programu a apamäť údajov
**Pamäť programu**:
- konečná usporiadaná množina registrov len na čítanie
- register programovej pamäti -> jednoznačne identifikovaný adresou
- register PC -> aktualizovaný po vykonaní inštrukcie
**Pamäť dát**:
- lineárne usporiadaná postupnosť pamäťových registrov
- $r_0$ -> akumulátor, uchováva výsledok operácie
**4 hlavy**:
Hlava na:
- vstupnej páske (čítanie)
- výstupnej páske (zápis)
- dátovej pamäti (čítanie aj zápis)
- pamäti programu (čítanie)
**Model pre určovanie zložitosti**:
- v porovnaní s architektúrou dnešných počítačov je značne zjednodušený
- vďaka zjednodušenia nemajú konštantné faktory veľkú výpovednú hodnotu -> použitie v [[Analýza algoritmov#Asymptotická notácia|asymptotickej zložitosti]]

### Abstrakcie RAM
Niekedy nepotrebujeme ani všetky jeho časti, preto aplikujeme niektoré ešte jednoduchšie modely -> *abstrakcie*

#### Lineárny model
Pri **lineárnych RAM programoch**, kde inštrukcie programu slúžia iba za účelom iterácie môžeme použiť jednu z abstrakcií. Takéto programy môžeme reprezentovať:
$$
P = h*k*l*t
$$
Kde:
- $h$ -> head (inštrukcie pred cyklom)
- $l$ -> loop
- $k$ -> počet iterácií (môže byť na vstupe)
- $t$ -> tail (inštrukcie po cykle)

Môžeme abstrahovať a vynechať niekoľko inštrukcií (skoky, inštrukcie vstupu a pod.	)

#### Bitový model
- zohľadňuje logaritmické kritérium
- narozdiel od [[#Lineárny model|lineárneho modela]] sa používajú bitové premenné a logické operácie
- rozmery operandov sú podstatné
- korešponduje s logickými obvodmi (počet krokov -> počet prvkov)

#### Porovnávací model
Pri niektorých programoch sú meradlom zložitosti momenty porovnávania (napr. triedenie). Uvažujeme model, kde každý krok predstavuje dvojcestné vetvenie -> preto je vhodná reprezentácia vo forme **rozhodovacieho stromu**.
#add_link 
- vnútorný vrchol reprezentuje rozhodovanie
- **vľavo** je podmienka **splnená**
- **vpravo** je podmienka **nesplnená**

Časová zložitosť daná výškou stromu:
- pre počet utriedených možností: $n!$, potom je zložitosť (výška stromu): $T(n) = log(n!) ~ log(n/e)^n ~ n*log(n)$

## Stroj RASP
Ide o model von neumanovského počítača.
#add_link 

RAM a RASP sú ekvivalentné z hľadiska časovej aj pamäťovej zložitosti

Rozlišnosti od [[#Stroj RAM]]:
- program je uložený spolu s údajmi
- má rovnaké inštrukcie, a len 2 typy operandov
- tvar inštrukcie: <operácia>\<operand> 
- môže modifikovať svoj kód
