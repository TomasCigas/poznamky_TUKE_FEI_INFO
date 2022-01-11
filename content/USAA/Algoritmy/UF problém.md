# UF problém
Jedná sa o vhodnú [[Údaje a údajové štruktúry|ÚŠ]] pre efektívne riešenie **UNION-FIND** problém na [[Práca s ADT množina|množinách]].

Príklad využitia: nájdenie minimalnej kostry grafu, spracovanie vrcholov

## Jednoduchý algoritumus
*Predpoklady*:
- Máme vzájomne disjunktné množiny $A,B$
- Snažíme sa nájsť množinu $C$, kde $C\leftarrow A \cup B$
- prvky množín považujeme za celé čísla

*Reprezentácia množín*:
- Budú reprezentované [[Zoznam|spájaným zoznamom]]
	- $R[i]$ -> meno množiny obsahujúce prvok $i$
	- $NEXT[i]$ -> odkaz na ďalší prvok množiny

*Ďalšie [[Údaje a údajové štruktúry|ÚŠ]]*:
- $LIST[i]$ -> prvá polzka množiny
- $SIZE[i]$ -> počet prvkov položky
- $EXT_N[i]$ -> **vonkajšie** meno množiny s vnútorným menom $i$
- $INT_N[i]$ -> **vnútorné** meno množiny s vonkajším menom $i$

*Návrh algoritmu*:
- realizácia $FIND(i)$: sprístupnenie položky $R[i]$ -> $O(1)$
- realizácia $UNION(A,B,C)$:
	- prehľadanie $R$, nájdenie $R[i]=A$ alebo $R[i]=B$, prepísanie obsahu $R[i]\rightarrow C$ -> $O(n)$ => pre $n$ operácií potom $O(n^2)$

*Zlepšenie algoritmu*
- využijeme vlastnosti spájaných zoznamov
- realizujeme zlučovanie dvoch množín začlenením menšej množiny do väčšej
	- využijeme zavedené 2 typy mien
	- $R[]$ bude obsahovať **vnútorné**, $UNION(A,B,C)$ zasa **vonkajšie**
- zložitosť máme teda v najhoršom prípade $O(n*log(n))$
- bez $EXT_N$ by výsledok UNION mal meno väčšej množiny
- vďaka sofistikovaných ÚŠ máme takmer lineárnu zložitosť

## Algoritmus s využitím stromovej reprezentácie

**Implementujeme** 2 polia:
- *parent* -> [[Zoznam]], ktorý uchováva referenciu na bezprostredného predcodcu
- *rank* -> Zoznam využívaný na obmedzenie maximálnej hĺbky stromov

*Inicializácia*:
- Každý prvok je sám blokom
- každý blok reprezentovaný stromom a charakterizovaný svojím reprezentantom
- každý prvok uchováva odkaz na predchodcu v strme

$FIND(i)$ -> vráti reprezentanta bloku
$LINK(i,j)$ -> spojí rôzne bloky ($i,j$ - reprezentanti)

*Jednoduché riešenie* takýmto spôsobom -> rekurzívne hľadanie rodiča je neefektívne, pretože potrebujeme opakovane prechádzať cestou "parent-ov" pri $FIND$

*Optimalizovanie*:
1. **Union by rank** -> obmedzenie hĺby stromov
	- Na začiatku má každý reprezentant $rank=0$
	- Po spojení 2 reprezentantov s rôznou hodnotou $rank$, sa stane reprezentant s **nižším** $rank$ **synom** reprezentanta s **vyšším** $rank$
		- pokiaľ majú rovnaký $rank$, rodiča zvolíme ľubovoľne a tým sa mu zvýší $rank$
2. **Path compression** -> zlepšenie postupnosti "parent"
	- pre $\forall$ vrcholy navštívené počas operácie $FIND(i)$ budú mať presmerovanú referenciu z "parent" rovno na reprezentanta $i$

Po optimalizácii máme teda zložitosť:
pri vykonávaní $m$ operácií $FIND$ a $n-1$ operácií $LINK$ -> $O(m*\alpha _T (m,n))$
$\alpha _T$ je konštanta.

Pre všetky hodnoty $n, \alpha _T (m,n) \leq 5$ má uvedený algoritmus prakticky konštantú zložitosť (na operáciu).

