# Reprezentácia stromov
[[Špeciálne typy grafov#Strom|Strom]] je špeciálny prípad orientovaných grafov.

Ide o mimoriadnu úlohu v programovaní.

## Binárny strom
[[Špeciálne typy digrafov#Binárne stromy|Binárny strom]] je strom, v ktorom každý vrchol má maximálne 2 synov (môže mať aj 1).

Reprezentácia
- **Poliami**
	- LSYN -> ľavý synovia
	- RSYN -> pravý synovia
- **Smerníkmi**:
	- vrchol má smerník na pravého a ľavého syna
- **Jedný poľom**
![[tree_arr.excalidraw]]
	- môžeme reprezentovať aj neúplný strom
	- veľmi efektívne :*
	
### Binárny vyhľadávací strom
Predpoklad usporiadania.
Podporuje INSERT,DELETE,MEMBER,MIN.

Používajú sa tu [[Práca s ADT množina|množiny]].

Využíva sa stratégia [[#Inorder|inorder]].

**Definícia**:
BVS pre množinu $S$ je označený binárny strom, kde pre každý vrchol označený prvkom $l(v)\epsilon S$ platí:
- $\forall$ vrchol $u$ v ľavom podstrome $l(u) < l(v)$
- $\forall$ vrchol $u$ v pravom podstrome $l(u) > l(v)$
- $\forall$ vrchol $a$ existuje jediný vrchol $v$, taký že $l(v) = a$

**Zložitosť** najhorší prípad -> $O(n^2)$, možno vylepšiť použitím **AVL** alebo **RB** stromami.

#### Optimálne BVS
**Optimálny BVS** je [[#Binárny vyhľadávací strom|binárny vyhľadávací strom]], ktorý poskytuje najmenší možný/očakávaný čas na nájdenie požadovaného prvku/prvkov.

**Rozdelenie**:
- Dynamický
	- strom môže byť modifikovaný, zvyčajne otáčaním
- Statický
	- nemení sa štruktúra stromu

Návrh ÚŠ pre efektívne spracovanie [[Práca s ADT množiny|množiny]].
**opns** obsahuje len MEMBER.

**Základné pojmy**:
- nech a1, a2, ..., an – prvky S usporiadané podľa veľkosti  
- $p_i$ – pravdepodobnosť výskytu MEMBER($a_i, S$) v $\sigma$, $i$ = 1, 2, ... n  
- $q_0$ – pravdepodobnosť výskytu MEMBER($a, S$) v $\sigma$, a < $a_1$
- $q_i$ – pravdepodobnosť výskytu MEMBER($a, S$) v $\sigma$, $a_i < a < a_i+1$
- $q_n$ – pravdepodobnosť výskytu MEMBER($a, S$) v $\sigma$, $a$ > $a_n$  
- pridaných n + 1 fiktívnych listov (pre prvky $U – S$): 0, 1, 2, ... n

**Cena BVS B (c(B))**:
- ak $a = l(v)$, počet navštívených vrcholov pre MEMBER$(a, S): d(v) + 1$  
- ak $a\notin S$, $a_i < a < a_i+1$, počet navštívených vrcholov: $d(i)$

**Konštrukcia**:
- technika [[Metódy návrhu efektívnych algoritmov#Dekompozícia rozdeľ a panuj|dekompozície]]
- $T_{i,j}$ -> BVS s minimálnou cenou, pre prvky od $i+1$ po $j$

**Postup**:
ROOTS(S) -> [[Metódy návrhu efektívnych algoritmov#Dynamické programovanie|dynamické programovanie]]
BUILDTREE(0,n) -> vytvorenie nášho stromu ([[Metódy návrhu efektívnych algoritmov#Rekurzia|rekurzia]])

**Zložitosť**:
- konštrukcia - $O(n^3)$
- vyhľadávanie (ROOTS) $O(n^3)$

#### Vyvážené stromy
[[#Binárny vyhľadávací strom|BVS]] stromy nazývame **dokonale vyváženým** ak počet vrcholov pravého a ľavého podstromu každého vrcholu s líši najviac o 1.

Náročné udržiavať tento strom udržiavať.

**Charakteristika**:
- obnova dokonalého vyváženia
- menej prísne kritéria vyváženia
- používame inorder

Na **AVL** možno v čase ($O(log(n))$) vykonávať:
- Member
- Insert
- Delete

**Veta**
AVL strom s $n$ vrcholmi má výšku najviac $2*log(n)$

Pri **insert/delete** môžu nastať 3 prípady:
- $h_L = h_R$ (neporušené)
- $h_L < h_R$ (neporušené)
- $h_L > h_R$ (treba rekonštruovať)

**Nevyváženosť**:
![[unbalanc.png]]
- operácia vyváženia (rotácie) je definovaná ako postupnosť zámen smerníkov:
	- jednoduchá rotácia (LL/RR)
	- dvojitá rotácia (LR/RL)

**Odstráňovanie** pokiaľ je vrchol:
- list -> jednoducho odstránime
- s 1 synom -> výmena, odstránenie
- s 2 synmi -> náhrada najpravejším z jeho ľavého podstromu
-> môžeme musieť vyvažovať

Prístupy tvorenia:
- [[#2-3 stromy]]
- (a,b) - stromy
- Red-black stromy (RB)

## 2-3 stromy
**2-3 strom** je strom, v ktorom každý nelistový vrchol má 2 alebo 3 synov a každá cesta od koreňa k listu má rovnakú dĺžku.

**Reprezentácia** [[Práca s ADT množina|množiny]] $S$:
- prvky sú priradené listom:
	- ako slovník
		- vzrastá zľava doprava
		- vhodný na vyhľadávanie
		- $L[v]$ -> najväčší prvok podstromu, ktorého koreňom je najľavejší syn $v$
		- $M[v]$ -> najväčší prvok podstromu, ktorého koreňom je druhý (zľava) syn $v$
	- metódou vhodnou pre operáciu UNION

2-3 stromy sú vhodné na implementáciu štruktúr:
- Slovník
- Prioritný fron
- Zlučovateľná halda
- Spájateľný front
, pri čom spracúvajú $n$ inštrukcií v čase $O(n*log(n))$, nie sú kompatibilné pre UNION a CAT, resp. SPLIT

**Operácie**:
- **Insert**
![[2-3_tree_ins.excalidraw]]
- **Delete**
![[2-3_delete.excalidraw]]

## B-stromy
B-strom je štandardná [[Údajové štruktúry a algoritmy pre vonkajśie pamäte#Údajové štruktúry|organizácia súborov]].

Jedná sa o efektívnu implementáciu [[#Binárny vyhľadávací strom|vyhľadávacích]] stromov:
- majú malú výšku
- operácie nad nimi pracujú len s blokmi na ceste z koreňa k listu
- udržiavajú príbuzné záznamy na rovnakom bloku dát
- garantujú určitú mieru zaplnenie každého bloku

B-strom rádu $m$ má vlastnosti:
- koreň je buď listom alebo má aspoň 2 synov
- každý vnútorný uzol okrem koreňa má počet synov medzi $[m/2]$ a $m$
- všetky listy sú na rovnakej úrovni => vźdy je [[#Vyvážené stromy|vyvážený]]

B-strom je zovšeobecnením [[#2-3 stromy|2-3 stromov]].

**Vyhľadávanie** -> [[Triedenie#Binárne vyhľadávanie|binárne vyhľadávanie]] v aktuálnom uzle

**Vkladanie** -> vyhľadáme list, kam daný záznam patrí, potom ho uložíme / pokiaľ nemáme miesto uzol rozdelíme na 2 a prostredný kľúč vložíme do uzla rodiča.

**Zložitosť**:
- cca $2+log_{m/2}(\frac{n}{b*b'})$, kde
	-  $b$ -> počet záznamov v bloku
	-  $b'$ -> počet párov v bloku 
	-  $m$ -> maximálny stupeň vnútorných vrcholov
	-  viacúrovňový riedky index zlepšuje výsledky

### B+ stromy
Jedná sa o variant [[#B-stromy|B-stromov]], ktorý sa používa oveľa častejšie ako B-strom.

Narozdiel od B-stromu:
- vkladajú B+stromy údaje len do listov
- v interných uzloch sú uložené vybrané hodnoty kľúčov a smerníky (čo podporuje vyhľadávanie)
- listové uzly môžu obsahovať $\geq$ ako $m$ záznamov
	- listy obsahujú taký počet záznamov aby bol uzol aspoň spolovice zaplnený
	- listy sú zväčša spojené obojsmerným zoznamom

**Vyhľadávanie**:
- podobne ako v B-strome s rozdielom, že jepotrebné postupovať až do listu

**Vkladanie**:
- najprv sa vyhľadáva list
- ak nie je uzol plný vložíme záznam
- pokiaľ je plný uzol:
	- rozdelíme záznamy rovnomerne do obidvhoch uzlov
	- aktualizujeme kľúč (najnižšia hodnota sa zapíše do rodiča)


## Systematické prechádzanie stromom
Pre strom $T=(V,E,r)$, $r$ -> koreň
### Preorder
- označ koreň $r$
- označ podstromy
![[BS-preorder.excalidraw]]
### Postorder
- označ podstromy
- označ koreň $r$
![[BS-postorder.excalidraw]]
### Inorder
- označ podstromy
- označ koreň $r$
- označ podstromy
![[BS-inorder.excalidraw]]