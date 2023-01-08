************
Náš problém ma ohraničenia/obmedzenia, ktoré nám určujú, či máme riešenie. Sú riešiteľné bežnými [[Problém bez informácií|search algoritmami]], ale vďaka obmedzeniam dokážeme vytvoriť aj lepšie.

Stav je definovaný premennými $X_i$, ktoré nadobúdajú hodnotu z domény $D$. Cieľový stav je teda stav, ktorého premenné spĺňajú všetky ohraničenia.

**Typ ohraničenia**:
- *Explicitné* - ohraničenia sú definované ako $\forall$ možné kombinácie premenných
- *Implicitné* - ohraničenie je definované ako $\forall$ nemožné stavy

- *Unárne ohraničenie* - ohraničenie pre 1 premennú
- *Binárne ohraničenie* - ohraničenie pre 2 premenné na seba súvisiace
- *Ohraničenie vyššieho rádu* - ohraničenie n premenných na seba súvisiacich

*Summary*:
- hľadáme cieľový stav, ktorý je definovaný ohraničiami
- základné riešenie je [[#Spätné vyhľadávanie|spätné vyhľadávanie]], plus rozšírenia
	- zoradenie
	- [[#Dopredná kontrola|filtrovanie]]
	- [[#Konzistencia hrán|hranová konzistencia]]

# [[Problém bez informácií#DFS|DFS]] a [[Problém bez informácií#BFS|BFS]]
Považujú sa za "slepé" algoritmy.

**DFS**:
- *Časová*: $O(d^n)$
- *Pamäťová*: $O(d^n)$
**BFS**:
- *Časová*: $O(d*n)$
- *Pamäťová*: $O(d^k*n^k)$
_nvm čo je d,n a k :P_

# Spätné vyhľadávanie 
Algoritmus overuje ohraničenia počas chodu algoritmu a pokiaľ sa nájde nesplnené ohraničenie stav zahadzuje.
Expanduje pomocou [[Problém bez informácií#DFS|DFS]].
Kontroluje konzistentnosť stavu (či stav neporušuje niektoré ohraničenie).

# Dopredná kontrola
Nádstavba [[#Spätné vyhľadávanie|spätného vyhľadávania]].

Redukuje $H(f)$ dosiaľ nedoiahnutých premenných.
Po priradení danej premennej verifikuje $H(f)$ susedných (spolu súvisiacich) dosiaľ nepriradených premenných a redukuje ho (ak sa dá).

# Konzistencia hrán
Nádstavba [[#Dopredná kontrola|doprednej kontroly]].
Hrana $X \rightarrow Y$ je konzistentnám, ak pre $\forall$ hodnotu z $x \epsilon X$ existuje aspoň jedna hodnota $y\epsilon Y$.
Jednoducho povedané $\forall$ hrana v grafe musí byť konzistentná.
Pri redukcii $H(f)$ musíme skontrolovať aj už okonotrolované hrany.

**Algoritmus**:
1. Pridáme hodnotu premennej
2. Zistíme konzistenciu hrán susedov $A$ a $B$
	1. Ak hrana $AB$ nie je konzistentná s hranou $BA$, tak redukujeme $H(f)$ hrany $A$
3. Ak je $H(f)$ hrany $B$ prázdny, vyberáme inú hodnotu premennej
4. Opakujeme od 1. dokedy nie sú všetky hrany konzistentné

**Časová náročnosť**: $O(e*d^3)$
**Pamäťová náročnosť**: $O(e)$

**Radenie premenných**:
- *Minimal remaining values* - Vyberáme premenné s najmenšou mohutnosťou $H(f)$
- *Least constraining values* - Vyberáme premennú, ktorá minimálne narúša $H(f)$ ostatných premenných
- *Fail-Fast ordering* - ?

**Rozšírenia**:
*Path-consistency* - Rozšírenie hranovej konzistencie o cestu medzi dvoma stavmi
- Riešenie je konzistentné ak $(A,a);(B,b)$, je hranovo konzistentné, tak $\exists x$, tak aj $(A,x);(B,x)$ je hranovo konzistentné
*K-konzistency* - path-consistency pre viacero premenných

# Alternatívne riešenie - Local Search
Alternatívy ku typickému prístupu rozšírenia DFS.
Algoritmy pracujú s nejakým úplným stavom (všetkym premenným sú priradené hodnoty), a potom pracujeme s týmito už priradenými hodnotami:
- najprv ich náhodne priradíme
- meníme 1 hodnotu
- nepoužívame zásobník

## Min-max konflikt
Priradzujeme premenným hodnoty s ľubovoľným počtom konfliktov (porušenia obmedzení). Po priradzení vyberáme novú hodnotu premennej, ktorá minimalizuje počet konfliktov (počet konfliktov zisťujeme **evaluačnou funkciou**).

? je schopný riešiť N-queens v konštantnom čase.
## Hill-climbing
Taktiež inicializujeme počiatočný stav. Kontrolujeme premenné a ak existuje lepší "sused" (hodnota) tak ho vyberieme. Pokračujeme dokedy sa nedostaneme na **lokálne maximum**.
Nevýhodou je, že konzistnentosť riešenia nie je jednoznačná, nakoľko môžeme nájsť lokálne maximum.

Algoritmus je greedy - nehľade na ďalší krok vyberá najbližší stav k cieľu.

Kvôli nekonzistentnosti riešenia existuje niekoľko variantov:
- **First-choice** - akonáhle sa nájde lepší stav, ihneď ho vráti (úplne greedy)
- **Stochastic** - na základe evaluačnej funkcie priradí susedom percento zvolenia
- **Random-restart** - akonáhle nájde algoritmus nejaké maximum sa reštartuje a hľadá od znova (s iným počiatkom), teoreticky zaručujeme dostatočným množstvom reštartov konzistentnosť

## Simulated annealing (simulované žíhanie)
Kombinácia [[#Hill-climbing|hill-climbing-u]] a random-walk (náhodných pohybov).
Funguje podobne ako stochastic hill-climb, avšak pravdepodobnosť výberu nižšie evaluovaného suseda klesá s iteráciou algoritmu, tzv. klesá teplota algoritmu (preto žíhanie).

S dostatočným klesaním teploty sa nachádza konzistentné riešenie.

## Local-beam
Narozdiel od [[#Hill-climbing|hill-climbing-u]] sa pracuje s $k$ začiatočnými stavmi, ktoré sa spracúvajú / expandujú (tu sa môže použiť aj hill-climb).

Postup:
1. Vygenerovanie $k$ náhodných stavov
2. Určíme potomkov týchto stavov
3. Ak sa v potomkovi nachádza riešenie, tak končíme
4. Inak vyberáme k-najlepších stavov a opakujeme od 2.

Pokiaľ vyberieme veľa, pri najhoršom všetkých potomkov jedného rodiča, tak môže byť algoritmus opäť citlivý na lokálne maximum, riešením je zasa *stochaistický* prístup, kde potomkom pridávame percentuálnu šancu na výber podľa ich evaluačnej funkcie.

## Genetické algoritmy
Je to pokročilý stochaistický local-beam
Potomok je generovaný ako kombinácia 2 stavov (rodičov).
Je to "Darwinov" prístup k hľadaniu riešenia.

**Postup**:
1. Inicializácia $k$ stavov
2. Kombinácia stavov:
	1. Máme počiatočnú populáciu (z $k$ stavov)
	2. Použijeme fitness funkciu (evaluačná funkcia rodiča na pravdepodobnosť kombinácie s iným rodičom)
	3. Selekcia - samotný výber rodičov
	4. Kríženie - časti rodičov sa medzi sebou vymenia a vzniknú nový potomkovia
	5. Mutácia - istá časť potomka zmutuje (zmení sa nejaká hodnota)
3. Pokračujeme 2. pokiaľ sme nenašli riešenie

Počiatočná populácia stavov musí byť prejavená takým spôsobom, aby sme mohli jej časti meniť ako medzi rodičmi, tak mutáciou. Obvykle je to string, alebo číslo.
