*********************************
Axiomatická sémantika zabezpečuje **korektnosť** programu bez testovania, ktoré nemusí odhaliť všetky chyby. Robí to pomocou **dôkazu**.

# Floyd-Hoareova logika

## Floydova verifikácia

Floydova verifikácia čiastočnej korektnosti sa vytvára:
1. Uvažujeme blokovú schému algoritmu
2. Pre každú hranu blokovej schémy konštruujeme tvrdenie - stav výpočtu
3. dokážeme, že pre každý element platí: *Ak platí niektoré tvrdenie pri hrane vstupujúcej do elementu, potom všetky tvrdenia pri hrane vystupujúcej z tohto elementu platia po vykonaníu výpočtu v elemente*
![[Tvrdenie.excalidraw]]
, kde $P$ je tvrdenie
4. Z indukcie na počet krokov vyplýva, že všetky tvrdenia sú pravdivé pri každom vykonaní programu
5. Algoritmus je **čiastočne korektný** - pri každom **terminujúcom** výpočte poskytuje korektné výsledky

## Hoareova logika
Hoare vychádzal z [[#Floydova verifikácia|Floydových]] princípov.
Umožňuje verifikovať programy písané **modulárnym** spôsobom. Používa sa ako základ pre axiomatickú sémantiku.

**Hoareova trojica**:
$$
\{P\}\ S\ \{R\}
$$
, kde:
- $P$ je predpodmienka
- $S$ je príkaz
- $R$ je postpodmienka
- $P,R$ sú tvrdenia

Čítame to ako:
*Ak $P$ je pravdivé v stave pred vykonaním $S$, potom $R$ bude pravdivé v stave po jeho vykonaní.*

Axiomatická sémantika **podmienky**:
![[Pasted image 20240121201947.png]]
Axiomatická sémantika **cyklu**:
![[Pasted image 20240121202003.png]]
, kde $\Theta$ je **invariantná vlastnosť**, alebo invariant cyklu.

Inak povedané $\Theta$ musí platiť:
- pred vykonaním celého cyklu
- pred vykonaním každej iterácie, spolu s pravdivou podmienkou
- po vykonaní každej iterácie
- po vykonaní celého cyklu aj s nepravdivou podmienkou cyklu


*********************************
