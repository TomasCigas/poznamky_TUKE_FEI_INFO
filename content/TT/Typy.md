***********
**Typ** je:
- **súbor hodnôt**, ktoré môže počítač reprezentovať
- **operácie** nad týmito hodnotami

Kontrola týchto typov je vykonávaná v [[Formálne jazyky|prekladačoch]] a [linkeroch](https://en.wikipedia.org/wiki/Linker_(computing).

# Základné typy
Najzákladnejšie typy používané v [[Typovaný NBL|T-NBL]] a [[Jednoducho typovaný lambda-kalkul|JTLK]] sú $Bool$ a $Nat$.

Rozšírenejšie základné (atomické) typy sú napríklad $Real, Char, String$, ktoré používa mnoho programovacích jazykov.

Kvôli veľkému množstvu možných atomických typov v programovacích jazykoch si definujeme množinu základných typov $A$.

Teda majme:
$$
\texttt{A} \in A
$$
kde $\texttt{A}$ je základný typ z množiny základných typov.

# Jednoduché typy
**Jednoduché typy** sa tvoria kombináciou [[#Základné typy|základných typov]] pomocou typových konštruktorov:
$$
\rightarrow\ +\ \times
$$

Dostávame teda try hlavné jednoduché typy = *typové výrazy*:
- $T_1 \rightarrow T_2$ : funkčný typ
- $T_1 + T_2$ : súčtový typ
- $T_1 \times T_2$ : súčinový typ

## Funkčné typy
Funkčný typ sa používa na typovanie abstrakcie funkcií:
$$
\lambda x:T_1.t : T_1 \rightarrow T_2
$$
Typový konštruktor je sprava asociatívny.

## Súčtové typy
Sumy alebo súčtové typy umožňujú pracovať s heterogénnymi skupinami hodnôt, kde hodnoty majú rovnaký význam, ale môžu mať iný výsledok, alebo aj dokonca iný typ.

Jediné funkcie na súčtových typoch sú **injekcie**. Čisté súčtové typy majú len dve možné hodnoty, teda sú binárne:
![[sum.excalidraw]]


Nakoľko povoľuje súčtový typ rôzne hodnoty a typy, môže dôjsť k [[Jazyky#Typovanie|nejednoznačnosti typov]]:
$$
\begin{align}
inr\ 5 : Nat + Nat\\
inr\ 5 : Bool + Nat\\
...
\end{align}
$$
Na zabezpečenie jednoznačnosti používame 3 metódy:
- dochádza k rekonštrukcii typov #add_link 
- využijeme podtypy, kde každý typ sa vzťahuje na najmenší možný typ (všetci sú rovnaký typ v podstate) #add_link 
- požadujeme aby programátor [[Lambda-kalkul#Pripísanie|explicitne pomenoval]] aký typ používa.

My budeme používať explicitné pomenovanie.
### Variant
Variant je rozšírenie súčtových typoch o návestia (podobne ako pri [[#Záznam|súčinoch]]).

Teda namiesto $T_1 + T_2$ píšeme $[lab_1 : T_1, lab_2 : T_2]$.

Explicitne budeme teda pomenovávať:
$$
inr\ t\ as\  T_1 + T_2 \text{ je teda } [lab_1=t]\ as\  [lab_1 : T_1, lab_2 : T_2].
$$
#### Špeciálne varianty
Varianty majú viacero využití, niektoré sú často používané a preto sú zadefinované osobitne.

##### Voliteľné hodnoty
Ide o možnosť neexistencie hodnoty v nejakom programe. Inak povedané premenná môže byť istého typu a hodnoty, alebo nemusí existovať:
$$
OptionalNat = [null : Unit,some : Nat]
$$
##### Enumerácia
Enumeračný typ je [[#Variant|variant]], ktorého každá hodnota je $unit$ (typu $Unit$). Teda záleží len na *návestí*.

##### Jednopoložkový variant
Ide o enkapsuláciu podobne ako pri [[#Súčinové typy|unárnom súčinovom type]], len s názvom.


## Súčinové typy

Súčinový typ rozširuje jazyk o možnosť tvorby n-tíc hodnôt s n typmi:
$$
\langle v_1,v_2\ ...\ v_n \rangle : T_1 \times T_2 \times\ ...\ \times T_n
$$
Tieto hodnoty môžeme získať z danej n-tice tzv. **projekciami**:
![[touple.excalidraw]]

Pokiaľ má súčinový typ len 2 hodnoty nazýva sa binárnym súčinovým typom.

Pokiaľ má avšak len jeden, hovoríme o **unárnom súčinovom type**, ktoré ma mnoho využití v praktickom programovaní, najčastejšie sa jedná o enkapsuláciu hodnoty a teda jej ochrany pred nechcenými zmenami.

#### Záznam
Záznam je rozšírenie [[#Súčinové typy|súčinového typu]] o takzvané *návestia*. Teda namiesto projekcie prostredníctvom poradia si každej hodnote priradíme návestie, či pomenovanie a projektujeme prostredníctvom nej:
$$
\langle label_1:T_1, label_2:T_2,\  ...\ ,label_n:T_n\rangle
$$
Zápis je následovný:
$$
\langle partno = 5524, cost = 45 \rangle : \langle partno:Nat,cost:Nat\rangle
$$

V mnohých programovacích jazykoch nezáleží na poradí položiek. My avšak budeme považovať inak zoradené položky ako rozdielny záznam.

# Jednotkový typ
Zavedieme si jednotkový typ $Unit$, ktorý bude mať jedinú premennú $unit$.

Tento typ sa používa pri práci s [[Vedľajšie účinky|vedľajšími účinkami]] a taktiež pri práci s [[#Odvodené typy|odvodenými typmi]].


#  Zoznamy
Zoznam je najznámejší **rekurzívny typ**, ktorý povoľuje mať konečnú k-ticu hodnôt, ktoré sú rovnakého typu. Taktiež narozdiel od [[#Súčtové typy|súčtových]] či [[#Súčinové typy|súčinových]] typoch je možné zmeniť počet, či poradie hodnôt dynamicky počas bežania programu.

Syntax zoznamov je (v [[Jednoducho typovaný lambda-kalkul|JTLK]]): 
![[Pasted image 20240107183407.png]]
# Referenčné typy
Referenčné typy umožňujú prácu s *heap* pamäťou, za použitia referencie adresy pamäte (viditeľné v programovacom jazyku C - pointer).

Teda ak chceme uložiť do pamäte hodnotu, môžeme:
- vložiť do zásobníka hodnotu pod premennou
- alokovať bunku v heape a odkazovať sa na ňu

![[Pasted image 20240107183616.png]]

**Základné operácie** na referenčných typoch teda zahŕňajú:
- *alkovoanie* - $ref:Nat \rightarrow Ref\ Nat$
	- priradí hodnote bunku a odkazuje sa na ňu
- *dereferencia* - $! : Ref\ Nat \rightarrow Nat$
	- opačne zoberie referenciu na bunku a vráti hodnotu
- *priradenie* - $:=\ :\ Ref\ Nat\rightarrow Unit$
	- priradí hodnotu bunke

V prípade referencií a alokácií je potrebné aj **dealokovať** hodnotu, nakoľko nechceme aby nám stála v pamäti najmä ak ju nepoužívame, alebo sa ukončuje program.

Z toho dôvodu existujú 2 spôsoby ako dealokovať:
- **Explicitne** - programátor jednoducho určí, kde a kedy ju chceme dealokovať
- **Garbage collector** - program automaticky zabúda bunky heapu, pokiaľ už nepotrebujeme danú hodnotu (obvykle na ňu nemáme referenciu), alebo sa končí program.

Na vyhodnotenie musíme hodnotu najprv dereferencovať.

Niektoré programovacie jazyky povoľujú **aritmetiku referencií**, čo dáva programátorovi väčšiu kontrolu heap pamäte, avšak navyšuje komplexitu a môže privádzať väčšiu náchylnosť k chybám.

Typ referencie je $Ref$ + typ hodnoty. Na rozlíšenie kontextu typovej kontroly pridáme aj kontext heap pamäte z dôvodov efektivity (najmä pri cykloch, kde sa rovnaká hodnota môže viackrát kontrolovať):
$$
\Gamma\ |\ \Sigma \vdash t:T
$$
kde $\Sigma$ je kontext heap pamäte.

V $\Sigma$ sa mapujú referenčné hodnoty k typu, napr.:
$$
\Sigma = (l=ref\ 1 \mapsto Nat)
$$
Na zaručenie [[Jazyky|typovej bezpečnosti]] existujú vety:
![[Pasted image 20240107192442.png]]

# Typová rekonštrukcia
Jedná sa o spätné [[Jazyky#Typovanie|typovanie]] netypovaných termov. Napríklad ak máme term $f\ 3$ vieme, že $3 : Nat$, takže funkcia $f$ bude $f: X \rightarrow Nat$, kde $X$ predstavuje **typovú premennú**.

Postup pri typovej rekonštrukcii:
![[Pasted image 20240108164806.png]]

Algoritmus **unifikácie** zisťuje akého typu je daný term. Určuje to prostredníctvom **najvšeobecnejšieho unifikátora** $\sigma_{mgu}$ (most general unificator) a **najvšeobecnejšieho typu**

$\sigma_{mgu}$ dostaneme postupom:
![[Pasted image 20240108165049.png]]

V skratke typujeme za použitia premenných (na doteraz neznáme typy), následne zadáme obmedzenia na dané typy a pri unifikácie dosadzujeme rovnosťami na unifikácii, dokým už nevieme ďalej unifikovať. Ako posledný krok dosadíme jednotlivé typy na typové premenné.

# Podtypy
Podtypy patria medzi často používané rozšírenie typového systému.

Hovoríme teda, že existuje jeden najväčší typ $\top$ , ktorý je **super-typ** každého typu a najmenší $\perp$, ktorý je **podtyp** každého typu. Teda každý typ iný typ má nejaký super-typ a podtyp.

Na zadefinovanie, ktorý typ je podtyp ktorého (prípadne super), zavedieme **podtypovú reláciu**, ktorá je:
$$
S <:T
$$
, kde:
- $S$ je podtypom $T$
- $T$ je super-typom $S$
- každá hodnota popísaná typom $S$ je popísaná aj typom $T$
- prvky typu $S$ tvoria podmnožinu typu $T$

Napríklad celé čísla $Int$ sú super typom prirodzených čísiel $Nat$ nakoľko môžeme použiť $Int$  namiesto $Nat$ tam, kde by sme chceli a mohli použiť len $Nat$, ale naopak to nemusí byť pravda:
$$
Int\ 5 + Int\ 5 = 10 <=> Nat\ 5 + Nat\ 5 = 10
$$
ale
$$
Int\ 4 - Int\ 6 = -2 <\neq> Nat\ 4 - Nat\ 6 = ??
$$
Podtypová relácia je [[Množiny a množinové relácie#Vlastnosti binárnych množín|reflexínva a tranzitívna]].

V prípade funkčných typov platí rovnaký princíp. Pokiaľ máme typ $S_1 \rightarrow S_2$ a vieme, že $T_1 <: S_1$ a $T_2 <: S_2$,, tak funkcia $S_1 \rightarrow S_2$ môže byť použitá tam, kde funkcia typu $T_1 \rightarrow T_2$.

Podtypy [[#Súčinové typy|súćinových typov]] sú taktiež podobné, avšak podtypom súčinového typu, je súčinový typ s viac položkami.

---