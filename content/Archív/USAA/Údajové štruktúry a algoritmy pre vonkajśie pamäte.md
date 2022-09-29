# Údajové štruktúry a algoritmy pre vonkajšie pamäti

Jedná sa o algoritmy údajov uložených na [[Pamäť#Hierarchia pamätí|vonkajšej(sekundárnej) pamäti]].

## Model vonkajších výpočtov
Množstvo údajov presahuje kapacitu hlavnej pamäti.
Používajú sa na to najmä *disky*, ktoré majú väčšiu kapacitu, avšak pomalšiu prístupovú dobu ako hlavná pamäť, kvôli tomu sa snažíme minimalizovať prístupu na disk.

**Diskové jednotky**:
- súbor -> súvislá postupnosť bajtov často rozfragmentovaná po disku
- disk -> niektoré záznamy sú dostupnejšie rýchlejšie ako iné

## Vonkajšie triedenie
Triedenie údajov uložených na periferných pamäťových zariadeniach.

### Priame zlučovanie
*fáza* -> operácia pri ktorej sa manipuluje s celou množinou údajov
*prechod* -> najmenší podproces

**Postup**:
Delíme našu začiatočnú postupnosť na polovice, dokým nedostaneme požadovanú veľkosť

**Zložitosť**:
- *časová*:
	- daná poćtom prechodov a počtom záznamov v jednom bloku -> $O(n*log_2(n)/b)$
		- n -> prvky
		- b -> počet záznamov v bloku
- *priestorová*:
	- $2*n$ prvkov

### Prirodzené zlučovanie
Snahou je získanie výhody, pokiaľ sú na začiatku údaje už čiastočne utriedené.

**Postup**:
- zlučujeme max. usporiadanú postupnosť -> behy, nie postupnosti s pevnou dĺžkou
- beh je teda usporiadaná postupnosť
- nech $a$ - pôvodný súbor a máme $b$ a $c$, 2 fázy:
	- distribúcia -> behy sú rovnomerne rozdeľované do $b$ a $c$
	- zlúčovanie -> číta sa po jednom behu z každého súboru

**Zložitosť**:
- celkový počet behov -> v každom prechode zmenšený na polovicu
- v najhoršom prípade sme na $O(n*log_2(n))$, teda sme na úrovni [[#Priame zlučovanie|priameho zlučovania]]

### Vyvážené viaccestné zlučovanie
Znižujeme počet prechodov rozdelením na viac ako 2 pásky (súbory).

Následne ich však musíme spájať.

Pokiaľ máme $N$ pások a $r$ behov vzniká nám postupnosť $r/N$ behov.

Používame rovnaký počet vstupných a výstupných pások.

**Zložitosť**:
- počet prechodov: $k=[log_N(n)]$
- počet opns kopírovania $O(n*[log_N(n)])$ (najhorší prípad)

### Polyfázové triedenie
Efektívnejšie využitie pások.

Nedodržujeme poćet prechdov.

Napr. pokiaľ mám 3 pásky:
- na každom prechode sa prvky zlučujú z 2 pások na 3.
- ak sa dosiahne koniec jednej z výstupných pások, táto s zmení na výstupnú
- $n$ behov vstupnej pásjy sa zmení na $n$ behov výstupnej -> udržiavame počet behov n každej páske

Pre $N$ pások algoritmus pracuje ako $(N-1)$-cestné zlučovanie

**Zložitosť**
- prechody $k=[log_N(n)]$

**Optimalizácia**:
- kombinácia vonkajšieho a vnútorného triedenia
- presúvame údaje v blokoch medzi internou a externou pamäťou

**Triedenie viaccestným zlučovaním**:
- lepšie využitie dostupnej internej pamäti
- zlučovanie viac ako dvoch behov -> redukcia počtu fáz

## Údajové štruktúry

**Organizácia súborov**:
- predpokladá sa, že súbor pozostáva z postupnosti záznamov, kde každý záznam je postupnosť polí
- všeobecne sa delia polia:
	- **fixná dĺžka (DBMS)**
	- premenlivá dĺžka (textové informácie)

**Základné operácie nad súbormi**:
- INSERT
- DELETE
- MODIFY (modifikácia všetkých záznamov s určenou hodnotou v každom z uvedených polí)
- RETRIEVE (vybranie všetkých záznamov, ktoré majú určenú hodnotu v každom z uvedených polí)

**Rozdiely v porovnaní s prístupom k prvkom množín**:
- súbory na externých zariadeniac -> zohľadnenie blokového prístupu, cenová metrika
- na záznamy v súbore môžu existovať smerníky
	- nemožné jednoducho posúvať záznamy v rámci súboru
	- jedná sa o pripichnutých (*pinned*) záznamoch
	- smerník na záznam:
		- fyzická adresa (začiatok bloku)
		- offset (boloha v rámci bloku)

*Štandardne sa používajú [[Reprezentácia stromov#B-stromy|B-stromy]].*

### Zoznam blokov
Jedná sa o najjednoduchšiu implementáciu. 

Záznamy sú uložené v ľubovoľnom poradí.

**OPNS**:
- **Retrieve** -> realizované sekvenčným prechodom
- **Insert**-> pripojenie záznamu na koniec
- **Modify** -> sekvenčný prechod
- **Delete** -> sekvenčný prechod
	- musíme záznam odstrániť logicky -> označiť, že záznam je zmazaný, aby sme ho mohli nahradiť

Veľmi neefektívne!

**Urýchlenie operácií**:
- predpokládame existenciu *kľúča* v zázname, aby sme limitovali sekvenčné prechádzanie
- priamy prístup k blokom (smerníky na jednotlivé bloky)

### Hašované súbory
- podobne ako [[Práca s ADT množina#Hashovanie|tu]]

Zoznamy rozdelíme do nádob -> realizované ako spájané zoznamy.

**Zložitosť**:
- často najrychlejšia metóda, nie je možné jednoducho sprístupniť záznamy v utriedenom poradí

### Indexové súbory
Súbor utriedený podľa kľúča. Celkom bežný spôsob.

Urýchľuje vyhľadávanie v takejto organizácii záznamov -> vytvorenie súboru: **riedky (sparse) index** -> pozostáva z párov $(x,b)$, kde:
- $b$ -> adresa bloku
- $x$ -> kľúč adresy
a je usporiadaný podľa hodnôt kľúčov.

![[index_file.excalidraw]]

**Vyhľadanie** záznamu:
- prehľadávame indexu, ke hľadáme najväčšie $z,z\leq x$, pre ktoré existuje $(z,b)$
- ak sa nachádza $x$ v súbore, potom je v bloku $b$
- stratégie prehľadávania:
	- lineárne
	- [[Triedenie#Binárne vyhľadávanie|binárne]] (rýchlejšie)

**Vloženie** záznamu:
- vyhľadávanie bloku $B$, pre uloženie s využitým indexom
- vložíme záznam ak máme miesto, inak vyhľadáme jeo následovníka a vložíme ho do ďalšieho bloku
	- ak je aj ďalší blok plný / resp. $B$ je posledný, požiadame OS o ďalší blok
- upravujeme index súboru

**Zložitosť**:
- pre $n$ záznamov cca $2+log(\frac{n}{b*b'})$, kde:
	-  $b$ -> počet záznamov v bloku
	-  $b'$ -> počet párov v bloku 

### Neutriedené súbory a hustý index
Neusporiadávame podľa kľúča, používame **hustý index**.

Pozostáva z párov $(x,p)$:
- $p$ -> smerník na záznam
- kľúč $x$

**Vyhľadávanie** záznamu -> hustý index ukazuje priamočiaro na náš aznam

**Vloženie** záznamu:
- udržiavame informáciu o poslednom bloku
- uložíme záznam do tohto bloku / požiadame o nový
- upravíme index

**Odstránenie** záznamu:
- nastavenie *flag* zmazania
- odstránenie položky z indexu

**Sekundárne indexy**:
- pomoc v prípade vyhľadávania záznamov podľa nekľúčových polí
- pozostáva z párov $(v,p)$: 
	- $v$ -> zoznam hodnôt pre polia
	- $p$ -> smerník na záznam
- vyhľadávame pomocou sekundárneho indexu
- je možné ušetriť miesto páry $(v,p_1),(v,p_2),(v,p_3)...$ nahradíme len zoznamom $p_1,p_2,p_3...$

**Použitie sekundárnych indexov**:
- nevýhodou sú náklady spojené s vytvorením sekundárneho indexu -> priestor na tieto indexy a úprava týchto súborov sú príliš náročné
- potrebujeme zvážiť ktoré záznamy budú mať svoj index
