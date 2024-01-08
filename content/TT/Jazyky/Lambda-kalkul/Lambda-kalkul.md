***********
$\lambda$-kalkul (ďalej len LK) je *formálny výpočtový systém*.

Čistý LK neobsahuje žiadne typy ani konštanty

Všetky výpočty LK sú redukované na základné 2 operácie:
- definícia funkcie
- aplikácia funkcie

Využitie:
- špecifikácia čŕt jazyka
- návrh jazyka
- implementácia jazyka
- štúdium typových systémov

LK je teda:
- jednoduchý jazyk na zápis výpočtov
- matematický objekt na dôkaz vlastností
# Funkcie
$\lambda$-kalkul poskytuje možnosť zápisu funkcie, ktorý je analogický ku matematickému zápisu:
$$
\begin{align}
(Matematicky):f(x)=x+1\\
(\lambda \text{-}kalkul):f = \lambda x.x+1
\end{align}
$$
kde $\lambda x$ je zadefinovanie argumentu.

LK je asociatívny sprava, teda ak máme termy $a,b,c$ a dáme ich vedľa seba:
$$
a\ b\ c
$$
ich aplikácia bude vyzerať takto:
$$
(a\ b)\ c
$$
Inak povedané najprv sa na funkciu $a$ aplikuje parameter $b$ a až potom $c$ (ak nie je určené zátvorkami inak).

Parametre funkcie môžu byť:
- **viazané**: premenná sa nachádza v tele funkcie
- **voľné** : premenná sa nenachádza v tele funkcie

Teda pre funkciu:
$$
\lambda x.\lambda y.x
$$
je $x$ viazaná a $y$ voľná.

# Syntax
Syntax čistého LK je jednoduchá:
$$
\begin{align}
t::= \ (\text{označenie pre $\lambda$ term})\\
x\ |\ (\text{ľubovoľná premenná})\\ 
\lambda x.t\ |\ (\text{abstrakcia funkcie})\\ 
t\ t\ |\ (\text{aplikácia funkcie})\\ 
(t) \ (\text{zátvorkový tvar})
\end{align}
$$
(!) Zátvorkový tvar sa používa na uzatvorenie celku funkcie (podobne ako v matematike)

V jednoduchosti teda:
$$
t::=\ x\ |\ \lambda x.t\ |\ t\ t\ |\ (t)
$$
# Termy
Term bez [[#Funkcie|voľných]] premenných sa nazývajú **uzavreté** alebo **kombinátory**.

Hodnoty sa musia vyjadriť ako funkcie v LK. Church zaviedol teda preddefinované termy, ktoré reprezentujú boolean a numerické hodnoty

## Boolovské termy
Termy pravdivostných hodnôt:
$$
\begin{gather}
tru = \lambda x.\lambda y.x \\
fls = \lambda x.\lambda y.y
\end{gather}
$$
Kombinátory pre tieto termy:
- **Testovací kombinátor**: $test = \lambda b. \lambda c. \lambda a.b\ c\ a$
- **Konjukcia**: $and = \lambda b. \lambda c. b\ c\ fls$
- **Disjunkcia**: $or = \lambda b. \lambda c. b\ tru\ (c\ tru\ fls)$
- **Negácia:** $not = \lambda b. b\ fls\ tru$
- **Dvojica**: $pair = \lambda f\ \lambda s. \lambda b. b\ f\ s$
	- prvá hodnota: $fst = \lambda p. p\ tru$
	- druhá hodnota: $snd = \lambda p. p\ fls$

## Čísla
Všetky čísla sa definujú ako následkom 0:
$$
\begin{align}
c_0 = \lambda s.\lambda z.z\\
c_1 = \lambda s.\lambda z.s\ z\\
c_2 = \lambda s.\lambda z.s(s\ z)\\
...
\end{align}
$$
Kombinátory:
- **Sčítanie:** $add = \lambda m. \lambda n. \lambda s. \lambda z. m\ s(n\ s\ z)$
- **Násobenie**: $times = \lambda m. \lambda n. \lambda s. \lambda z. m\ (add\ n)\ c_0$
- Ďalšie: ![[Pasted image 20240104152835.png]]
## Fixný bod a rekurzia
Nakoľko nie je možné použiť funkciu pred jej zadefinovaním (rovnako ako aj hodnotu) na využitie rekurzie v LK sa používa tzv. **fixný bod**. Tento fixný bod zaručuje opakovanie funkcie.

Existuje viacero kombinátorov fixného bodu. Avšak nakoľko používame metódu volania menom (*call-by-name*) budeme používať **zovšeobecnený kombinátor fixného bodu**.
$$
fix = \lambda f.(\lambda x. f(\lambda y. x\ x\ y))\ (\lambda x.f(\lambda y. x\ x\ y))
$$
Tento kombinátor vychádza z princípu nekonečne [[#Vyhodnotenie|redukovateľnej]] funkcie $\Omega$:
$$
\begin{gather}
\Omega = \omega\ \omega = (\lambda x.x\ x)\ (\lambda x.x\ x)\\
(\lambda x.x\ x)\ (\lambda x.x\ x) \rightarrow_\beta (\lambda x.x\ x)\ (\lambda x.x\ x) \rightarrow_\beta (\lambda x.x\ x)\ (\lambda x.x\ x) \rightarrow_\beta\  ...
\end{gather}
$$
Fixný kombinátor funguje následovne:
**Pre $\forall$ termy $h$ (funkcie) $\exists$ term $t$ (fixný bod) taký, že platí:**
$$
h\ t=t
$$
(!) Dôkaz je ugh:
![[Pasted image 20240104153722.png]]


## Odvodené tvary termnov
Ide o jednoduchší a viac čitateľný spôsob zápisu niektorých termov.

### Zoradenie
Zoradenie je vyhodnotenie termov za sebou, pri čom však predpokladáme, že prvotné termy majú [[Vedľajšie účinky|vedľajšie účinky]], a preto majú hodnotu $unit$, ktorá je zahoditeľná a nebude sa vedľajši účinok propagovať:
$$
t_1;t_2
$$
,kde $t_1 \rightarrow^* unit$.

Formálny zápis zoradenia je:
$$
(\lambda x:Unit.t_2)\ t_1
$$
### Zastúpenie
Ide o prázdnu abstrakciu, kde vkladaný parameter je v terme voľný a teda nemá zmysel sa ho vyhodnocovať:
$$
\lambda\_ : S.t
$$
Pri čom formálny spôsob zápisu je podobný:
$$
\lambda x : S.t
$$
, kde $x:S$ sa v $t$ nevyskytuje.

! Stále je ale potrebné určit typ prázdneho parametra

### Let-väzba
Je rozšírenie o lepšie čitateľnú abstrakciu:
$$
\begin{gather}
let\ x = t_1\ in\ t_2\\
(\lambda x:T_1.t_2)\ t_1
\end{gather}
$$
, kde oba zápisy sú ekvivalentné.

V tomto prípade sa vyhodnotí term $t_1$ ako prvý a potom sa priradí hodnote $x$ v terme $t_2$.

Pri kontrole typov doplní typechecker žiadanú informáciu na základe svojej analýzy (ide teda o transformáciu [[Jazyky#Typovanie|odvodenia typov]])

### Pripísanie
Pripísanie je **explicitné priradenie typu** určitému termu. Vykonáva sa kvôli nejednoznačnosti napr. [[Typy#Jednoduché typy|súčtových typov]].

Zápis je jednoduchý:
$$
t\ as\ T : T
$$

### Case-väzba
Používa sa výhradne v [[Typy#Súčtové typy|súčtových typoch]], kde každej injekcii, či návestí priradzuje istý term:
$$
case\ t_1:T_1\ of\ t_2 : T_2
$$

# Vyhodnotenie

Vyhodnotenie LK je pomerne jednoduché. Sémantický význam LK termu nachádzame pomocou **redukcie** na najmenší možný term, teda dokým už nevieme ďalej redukovať

## $\beta$-redukcia
Najjednoduchšia redukcia, spočíva v aplikácii termu na parameter.

## $\alpha$-redukcia
Pokiaľ by sa redukciou premenná stala viazaná na zlú funkciu používame $\alpha$-redukciu.

Napríklad ak by sme redukovali term pomocou [[#$ beta$-redukcia|beta-redukcie]]:
$$
(\lambda x.(\lambda \underline{y}.x\ \underline{y}))y \rightarrow_\beta \lambda y.y\ y
$$

Spočíva v jednoduchej zmene názvu premennej:
$$
(\lambda x.(\lambda \underline{y}.x\ \underline{y}))y \rightarrow_\alpha (\lambda x.(\lambda \underline{z}.x\ \underline{z}))y \rightarrow_\beta \lambda z.y\ z
$$
## $\eta$-redukcia
Odstraňuje voľné premenné z funkcií. Teda ak term $t$ nemá parameter $x$, tak sa bude redukovať:
$$
\lambda x.t\ x \rightarrow_\eta t
$$

---
- [[Jednoducho typovaný lambda-kalkul]]
- [[Curry-Howardova korešpondencia]]
---