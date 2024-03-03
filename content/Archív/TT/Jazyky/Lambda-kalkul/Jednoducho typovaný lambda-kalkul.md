***********
Jednoducho typovaný $\lambda$-kalkuk (ďalej JTLK) je najjednoduchším typovaným programovacím jazykom. je rozšírením [[Lambda-kalkul|LK]] o typy. Rovnako je doplnený o tvary termov jazyka [[Typovaný NBL|T-NBL]] (if).


# Vlastnosti
JTLK je [[Jazyky#Typovanie|jednoznačný a bezpečný]]. 

## Jednoznačnosť
JTLK má v typovom kontexte $\Gamma$ pre term $t$ najviac jeden typ $T$, pre ktoré platí:
$$
\Gamma \vdash t : T
$$
## Progresia
### Veta o kanonických tvaroch hodnôt
- Ak je $v$ hodnota typu $Bool$, potom nadobúda hodnoty $true$ alebo $false$
- Ak je $nv$ hodnota typu $Nat$, potom je $nv$ buď 0 alebo $succ(nv)$
- Ak je $v$ hodnota typu $T_1 \rightarrow T_2$, potom $v = \lambda x:T_1.t_2$ 
### Veta o progresii
Ak je $t$ uzavretý a správne typovaný term $\vdash t:T$, pre určitý typ $T$,
tak potom je $t$ buď hodnota, alebo exituje term $t'$, ktorý vzniká redukciou $t \rightarrow t'$
## Stabilita
### Veta o komutatívnosti typového kontextu
Nech máme $\Gamma \vdash t :T$ a $\Delta$ je permutáciou množiny $\Gamma$. Potom $\Delta \vdash t : T$ je rovnaký term. V prípade [[Jazyky#Typovanie|typovania]] sa hĺbka stromu nemení.

Inak povedané nezáleží na poradí deklarácií v typovom kontexte.
### Veta o zoslabení
Nech máme $\Gamma \vdash t :T$ a $x:S$ je [[Lambda-kalkul#Funkcie|voľná premenná]]. Potom $\Gamma, x:S \vdash t : T$ je term s rovnakou hĺbkou ako pôvodný strom.

Jednoducho nezáleží či máme v kontexte niektoré premenné navyše.
### Veta o zachovaní typov substitúciou
Ak máme termy $\Gamma, x:S \vdash t : T$ a $\Gamma \vdash s : S$, potom substitúciou termu $s$ za premennú $x$ sa typ termu $t$ nezmení:
$$
\Gamma \vdash [x \mapsto s]t : T
$$
### Veta o stabilite
Ak máme term $\Gamma \vdash t : T$ a term $t$ sa redukuje v jednom kroku na $t'$ ($t \rightarrow t'$), potom:
$$
\Gamma \vdash t' : T
$$
je term toho istého typu.
## Inverzia
Veta o inverzii vyjadruje *inverznú vlastnosť typovania* je JTLK:
Nech $\Gamma$ je typovaný kontext a $T_1,T_2,T_3,T_4$ sú jednoduché typy, potom:
1. Ak $\Gamma \vdash x:T_1$ , potom $x:T_1 \in \Gamma$
2. Ak $\Gamma \vdash \lambda x:T_1.t_2:T_2$, potom $T_2 = T_1 \rightarrow T_3$, pre určitý typ $T_3$ taký, že $\Gamma, x:T_1 \vdash t_2 : T_3$
3. Ak $\Gamma \vdash t_1\ t_2 : T_1$, potom existuje typ $T_4$, taký, že $\Gamma \vdash t_1:T_4 \rightarrow T_1$ a $\Gamma \vdash t_2 : T_4$
4. Ak $\Gamma \vdash true :T_1$, tak $T_1 = Bool$
5. Ak $\Gamma \vdash false :T_1$, tak $T_1 = Bool$
6. Ak $\Gamma \vdash 0 :T_1$, tak $T_1 = Nat$
7. Ak $\Gamma \vdash if\ t_1\ then\ t_2\ else\ t_3 :T_1$, potom $\Gamma \vdash t_1 : Bool$ , $\Gamma \vdash t_2 : T_1$ a $\Gamma \vdash t_3 : T_1$


---
