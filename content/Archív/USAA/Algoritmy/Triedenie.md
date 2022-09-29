# Triedenie
Preusporiadanie prvkov postupnosti tak by boli v neklesajúcom/nevrzastajúcom poradí.

Potrebujeme vedieť nad našou vstupnou [[Čiastočne usporiadané množiny|postupnosťou]] [[Množiny a množinové relácie|reláciu]], podľa ktorej ju budeme triediť.

**Zložitosti**:
![[algorithms.jpg]]

## Metódy triedenia
- **Vnútorné** -> údaje v hlavnej pamäti
- **Vonkajšie** -> údaje z časti v hlavnej pamäti, zväčša v sekundárnej

## Triedy algoritmov

### Znalosť štruktúry
Vieme niečo o štruktúre prvkov

#### RadixSort
Triedime postupnosť čísel z intervalu $<0,m-1>$

**Postup**:
- inicializácia $m$ frontov
- prechod postupnosťou prvok $a$ v $a-tom$ fronte
- **triedenie prvkov podľa cifry** alebo v prípade abecedného ideme po **lexigrafickom poradí podľa písmena**
- spojenie frontov do jedného -> výsledok

**Zložitosť**:
- vkladanie prvkov do frontov -> $O(n)$
- zreťazenie frontov -> $O(m)$
- triedenie pokiaľ $m$ je $O(n)$ -> $O(n)$

### Neznalosť štruktúry
Nevieme nič o štruktúre.
Najhoršia/Očakávaná zložitosť -> $O(n*log(n))$

#### Triedenie porovnaním
Jediná informácia ktorú využívame je získaná porovnaním dvoch prvkov

Algoritmus je v tvare [[Reprezentácia stromov#Binárny strom|binárnych stromov]].

#### SelectionSort
Triedenie **priamym výberom**.

**Metóda**:
Výber najmenšieho prvku zostávajúcej čast ($A[i+1]...A[n]$) a jeho výmena s aktuálnou pozíciou ($A[i]$).

**Zložitosť**
- celková -> $O(n^2)$

#### HeapSort
Triedenie **haldou**.

Využívame [[Reprezentácia stromov#Binárny strom|binárne stromy]], kde aždý list má hĺbku $d$ alebo $d-1$, kde $d$ je výška stromu.

**Halda** -> zaznačenie otca je väćšie/rovné ako značenie synov => najväčší prvok je v koreni.

**Metóda**:
Využitie procedúr: 
- HEAPIFY$(i,j)$, kde $i,j$ je interval s vlastnosťou haldy; $i$ -> koreň vytváranej haldy  
- BUILDHEAP vytvára nám haldu v lineárnom čase

**Zložitosť**:
- HEAPIFY ->  $T(h) = O(h)$, $h<log(n)$
- BUILDHEAP -> max $O(n/2^{i+1})$
- celkový algoritmus -> $O(n*log(n))$

#### InsertionSort
Dokáže nám zistiť $k$-ty najmenší/najväčší prvok.

**Metóda**:
$A[i]$ -> vlkadaný prvok, prvky v ľavo od $i$ sú už utriedené, pole sa indexuje od 0

**Zložitosť**:
$O(n^2)$

#### QuickSort
**Základný** tirediaci algoritmus.

**Výhody**:
- všeobecné použitie
- jednoduchá implementácia
- nenáročnosť zdrojov
- 2-3x rýchlejší ako [[#HeapSort]] a môže byť rýchlejší ako [[#MergeSort]]

**Nevýhody**:
- rekurzia môže byť nevýhodov
- má najhoršiu zložitosť ($O(n^2)$) \[očakávaná je však $O(n*log(n))$ \]

**Metóda**:
Vyberie sa z našej postupnosti tzv. **pivot**, pomocou ktorého sa **rozdelí postupnosť** na dve podskupiny (podľa toho či sú väčšie alebo menšie). Tento proces sa robí rekurzívne.

**Výber pivota**:
- tendencia zjednoduśenia náhodného výberu
- medián z časti postupnosti

#### MergeSort
#add_info 

### Výber $k$-tého najmenšieho prvku postupnosti
Ide o problém príbuzný najmenšieho prvku postupnosti.

**Zrejmá  zložitosť**:
- $O(n*log(n))$
- $O(n)$ ak použijeme [[Metódy návrhu efektívnych algoritmov#Dekompozícia rozdeľ a panuj|dekompozíciu]]

### Binárne vyhľadávanie
Pokiaľ máme v **opns** len operáciu MEMBER.

Predpokladom je existencia lineárneho usporiadania na $S$ (napr. $\leq$).

Rozhodujeme sa podľa "stredov":
![[binary_search.excalidraw]]
