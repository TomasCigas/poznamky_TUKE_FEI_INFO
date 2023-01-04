************
Náš problém ma ohraničenia/obmedzenia, ktoré nám určujú, či máme riešenie. Sú riešiteľné bežnými [[Problém bez informácií|search algoritmami]], ale vďaka obmedzeniam dokážeme vytvoriť aj lepšie.

Stav je definovaný premennými $X_i$, ktoré nadobúdajú hodnotu z domény $D$. Cieľový stav je teda stav, ktorého premenné spĺňajú všetky ohraničenia.

**Typ ohraničenia**:
- *Explicitné* - ohraničenia sú definované ako $\forall$ možné kombinácie premenných
- *Implicitné* - ohraničenie je definované ako $\forall$ nemožné stavy

- *Unárne ohraničenie* - ohraničenie pre 1 premennú
- *Binárne ohraničenie* - ohraničenie pre 2 premenné na seba súvisiace
- *Ohraničenie vyššieho rádu* - ohraničenie n premenných na seba súvisiacich

**Diskrétne premenné**:
- $H(f)$ má konečný počet prvkov
#add_info 

# [[Problém bez informácií#DFS|DFS]] a [[Problém bez informácií#BFS|BFS]]
Považujú sa za "slepé" algoritmy.

**DFS**:
- *Časová*: $O(d^n)$
- *Pamäťová*: $O(d^n)$
**BFS**:
- *Časová*: $O(d*n)$
- *Pamäťová*: $O(d^k*n^k)$
#add_info 

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

**Časová náročnosť**: $O(e*d^3)$
**Pamäťová náročnosť**: $O(e)$
