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

## Automaty
### Deterministické konečno-stavové automaty
[[#Gramatika|Gramatiky]] špecifikujú [[#Jazyk generovaný gramatikou|jazyky]] *generatívnym spôsobom*.
**Deterministické konečno-stavové automaty** je usporiadaná pätica $M=(Q,T,\theta , q_0,F)$, kde:
- $Q$ -> konečná množina stavov
- $T$ -> konečná množina vstupných symbolov
- $\theta$ -> prechodová funkcia automatu
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
