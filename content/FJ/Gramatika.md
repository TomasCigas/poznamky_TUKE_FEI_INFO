# Gramatika
Gramatika je usporiadaná štvorica $G = (N,T,P,S)$, kde:
- $N$ -> množina neterminálov
- $T$ -> množina terminálov
- $P$ -> množina pravidiel, ktorá určuje rozklad neterminálov na ďalšie neterminály alebo terminály
- $S$ -> je začiatočný symbol gramatiky, pri čom $S \in N$

**Krok odvodenia** je relácia, ktorú dosiahneme aplikovaním jedného z pravidiel $P$ na reťaz vytvorený gramatikou.
- opačne môžeme teda tvrdiť, že reťazec $a$ sa dá odvodiť z reťazca $a_k$, ak sa dokážeme dostať z reťazca $a$ do $a_k$ v $k$ krokoch. $k$ sa nazýva *dĺžka odvodenia*
_! informácie sú poľudštené, obsahuje to kopu matematických relačných termínov a definícií_

Každý reťazec, ktorý je možné odvodiť zo začiatočného symbolu, sa nazýva **vetná forma**.

**Jednoznačná gramatika** je gramatika, kde ku každému slovu z jazyka existuje práve jeden [[#Strom odvodenia|strom odvodenia]], v opačnom prípade hovoríme o nejednoznačnej/viacznačnej gramatike.
- nejednoznačné gramatiky spôsobujú problém pri tvorení kompilátorov
- ak by jedno slovo malo viac významov, môže dôjsť ku chybe pri prekladaní, kde nastane sémantická chyba

**Princíp vyčlenenia zľava** -> ak v gramatike existujú aspoň dve pravidlá pre neterminálny symbol a pritom majú rovnakú predponu pri odvodení a jeden symbol z nich je rozlišný, tak ich vieme rozdeliť zavedením nového neterminálu. Tak pokračujeme dokedy to nie je už možné:
$$
\begin{align}
A \rightarrow \alpha X_1 \beta _1 \\
A \rightarrow \alpha X_2 \beta _2 \\
............... \\
A \rightarrow \alpha X_n \beta _n \\
\end{align}
$$
Aspoň jeden $X_k$ je rôzny od ostatných symblov, tak:
$$
\begin{align}
A \rightarrow \alpha B \\
B \rightarrow X_1 \beta _1 \\
B \rightarrow X_2 \beta _2 \\
.............. \\
B \leftarrow X_n \beta _n \\
\end{align}
$$
Kde pravidlá z B, môžu byť tiež v podobnom tvare ako boli A predtým.

Tieto metódy však fungujú len pri deterministickej [[Syntaktická analýza|syntaktická analýza]], keďže nám v mnohých prípadoch zostanú aspoň 2 pravidlá pre 1 neterminál.

## Jazyk generovaný gramatikou
**Jazyk generovaný gramatikou** je množina všetkých takých reťazcov pozostávajúcich z terminálnych symbolov, ktorú dosiahneme odvodzovaním zo začiatočného symbolu gramatiky.

Jeden jazyk nemusí byť tvorený jedinou gramatikou. V tomto prípade má zmysel rozprávať o **ekvivalentných gramatikách**, kde 
$$
L(G1) = L(G2)
$$
$$
G1 \equiv G2
$$

## Klasifikácia
Podľa N. Chomského:
**Frázová** -> Na prepisovaných pravidiel nekladú ďalšie obmedzenia

**Kontextová** -> Každé prepisovacie pravidlo je v tvare $A\rightarrow B$, kde $A$ môže byť terminál aj neterminál a $B$ je terminál alebo neterminál a dĺžka pravej strany nesmie byť dlhšia ako dĺžka pravej strany. 
- inak, aby sme aplikovali pravidlo potrebujeme vedieť kontext okolo, ktorého existuje $A$
$\alpha A \beta$ -> $\alpha x \beta$, kde $\alpha$ a $\beta$ predstavuje ten kontext

**Bezkontextová** -> Každé prepisovacie pravidlo v tvare $A\rightarrow B$, kde $A$ je terminál a $B$ je mix terminálov alebo neterminálov

**Regulárna** -> Každé prepisovacie pravidlo v tvare:
	- $A\rightarrow bB$ a $A\rightarrow B$ alebo
	- $A\rightarrow Bb$ a $A\rightarrow B$
- regulárna gramatika je podstatná na tvorenie programovacích jazykov

Medzi týmito gramatikami plati závislosť:
$$
L(G3) \subseteq L(G2) \subseteq L(G1) \subseteq L(G0)
$$

### Strom odvodenia
Ohodnotený strom je **strom odvodenia**/derivačný strom, ak spĺňa podmienky:
- Každý vrchol je terminál či neterminál (+$\epsilon$)
- Koreň je $S$
- Potomky vrcholu musia spĺnať $P$
- Listy sú len terminály (+$\epsilon$)
- Slovo sa dá získať zreťazením listov 

## Automaty
### Deterministické konečno-stavové automaty
[[#Gramatika|Gramatiky]] špecifikujú [[#Jazyk generovaný gramatikou|jazyky]] *generatívnym spôsobom*.
**Deterministické konečno-stavové automaty** je usporiadaná pätica $M=(Q,T,\delta , q_0,F)$, kde:
- $Q$ -> konečná množina stavov
- $T$ -> konečná množina vstupných symbolov
- $\delta$ -> prechodová funkcia automatu
- $q_0$ -> začiatočný stav
- $F$ -> množina akceptujúcich/konečných stavov

**Konfigurácia konečného automatu** je usporiadaná dvojica $(q,w)$ predstavujúca nasledujúci stav, kde
- $q$ je momentálny stav
- $w$ je vstupný reťazec
- špeciálne typy:
	- *začiatočná konfigurácia* -> $(q_0,w)$
	- *akceptujúca konfigurácia* -> $(q,w)\in F$

### Nedeterministické konečno-stavové automaty
Podobná usporiadaná pätica ako pri [[#Deterministické konečno-stavové automaty|deterministických]].

Rozlišuje sa od determin., že môže prechádzať aj do iného stavu ak na vstup vložíme $\epsilon$, teda číta alebo nečíta vstupný reťazec.

#### Zásobníkové automaty
V tomto prípade je to usporiadaná sedmica:
$M=(Q,T,\gamma ,\delta ,q_0,Z_0,F)$, kde
- $Q$ -> konečná množina stavov
- $T$ -> konečná množina vstupných symbolov
- $\gamma$ -> konečná množina zásobníkových symbolov
- $\delta$ -> prechodová funkcia automatu
	- $\delta : Q\times T_\epsilon \times \gamma _\epsilon \rightarrow 2^{Q\times T*}_{kon}$
- $q_0$ -> začiatočný stav
- $Z_0$ ->Zásobníkový symbol nachádzajúci sa na začiatku $\gamma$
- $F$ -> množina akceptujúcich/konečných stavov
( trochu zastaralé )

Pracuje diskrétne, v každom kroku sa prečíta symbol z pásky, alebo pri čítaní $\epsilon$-u sa prečíta symbol zo zásobníka, ktorý sa dopĺňa pri postupe.

**Konfigurácia** je rozšírená aj o zásobníkový stav

## Jazykový procesor
Jazykový procesor je softvér, ktroý spracúva počítačové jazyky
Jeho hlavné úlohy:
- transformácia dokumentu/programu z jedného jazyka do druhého
- spracovanie dokumentu v istm jazyku

Jazykové procesory majú dve základné kategórie:
- **Kompilátory** -> trasnformujú z vyšších do mechanických
- **Interpretátory** -> priamo vykonávajú zápis vo vyššom
A ostatné:
- **Dekompilátory**
- **Prekladače**
- **Krížové prekladače** -> platformové prekladače
- **Bootstrap prekladače** -> špecifické pre istý jazyk
- **JIT kompilátory** -> kompilujú pri spustení
- **Byte-code kompilátory** -> kompilujú do symbolických inštrukcií

### Kompilátory
Podľa cieľového jazyka rozlišujeme:
- **Čistý strojový jazyk** -> Nevyužíva služby OS
- **Rozšírený strojový jazyk** -> využíva aj OS aj knižnice
- **Virtuálny strojový jazyk**

![[kompilátor.excalidraw]]
[[Lexikálna analýza|Lexikárny analyzátor]]

Podľa prístupu k [[Sémantická analýza|sémantickému spracovaniu]] kódu možno [[Gramatika#Kompilátory|kompilátory]] rozdeliť na:
**Jednoprechodový kompilátor** -> [[Lexikálna analýza|lexikálna]], [[Syntaktická analýza|syntaktická]] a sémantická analýza sa prekrývajú v čase
**Jednoprechodový analyzátor syntezujúci [[Medzikód|medzikód]] + prechod generujúci kód**
**Kompilátor využívajúci viacprechodovú analýzu** -> využíva sa, keď programovací jazyk nepotrebuje, aby bol identifikátor najprv deklarovaný
**Kompilátor využívajúci viacprechodovú syntézu**:
- jeden prechod generuje kód a druhý ho optimalizuje
- jeden prechod generuje asembler kód a druhý realizuje spracovanie kódu prekladačom asemblera

**Tabuľka symbolov** -> je to tabuľka obsahujúca lexikálnu implementáciu symbolov -> tokény (teda obsahuje informáciu o tom, aký token predstavuje aké symbol(y) )
- predvyplnenie tabuľky symbolov urýchľuje lexikálnu analýzu
- Typy:
	1. *Ohraničená* -> jednoduchá, problematická pri veľkom množstve identifikátorov a ich pomenovaniach
	2. *S premenlivou dĺžkou* -> flexibílna, horšie spravovanie
- Implementácie
	1. *Lineárny zoznam* -> jednoduchá implementácia, dlhé vyhľadávanie
	2. *Hashovacia tabuĺka* -> komplikovaná implementácia, krátke vyhľadávanie

#### Cieľové jazyky
Formáty:
- **Asembler** -> symbolický formát
- **Relokovaný** -> binárny formát
- **Pamäťový obraz** -> umiestenie do pamäte



