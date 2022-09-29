# Práca s ADT množina
Všeobecný postup pre návrh efektívneho algoritmu -> preskúmanie fundametnálnej povahy riešeného problému.

**Operácie na množinách**:
- Member
- Insert
- Delete
- Union
- Find
- Split
- Min

Množiny sa používajú na riešenie veľa problémov.

## Hashovanie
Ide o problém spracovania množiny $S$.

**Hashovanie** je technika spracovania údajov, aby sme mohli efektívne používať operácie Member, Delete, Insert.

Využíva sa **hashovacia funkcia** $h$, ktorá mapuje prvky na čísla z rozsahu $[0,m-1]$
$$
h:U\rightarrow [0,m-1]
$$
Kde:
$U$ -> univerzálna výberová množina

**Metóda**:
Majme pole $A$ o veľkosti $m$, ktorá obsahuje smerníky na zoznamy prvkov.
Naša hashovacia funkcia bude ukládať prvky do $A$ podľa jej výsledku.
![[hashing.excalidraw]]

**Zložitosť**:
- Najhorší prípad ($\forall$ prvky sú v 1 zozname) -> $O(n^2)$
- Priemerný prípad -> $O(1)$
- Očakávaná zložitosť -> $O(n)$

### Hashovacie funkcie
**Vlastnosti**:
- nízka zložitosť
- nízka miera [[#Riešenie kolízií|kolízií]]

Ideálna hashovacia funkcia-> každý kľúč má rovnakú pravdepodobnosť byť umiestnený v ktoromkoľvek zozname

#### Metódy
##### Delenie
Funguje na základe výpočtu zvyšku po delení:
$$
h(k) = k mod m
$$

Kritické miesto je výber čísla $m$, teda ktorým to budeme deliť.
Vlastnosti $m$:
- prvočíslo
- nie je deliteľom čísla $r^l \pm a$
	- $r$ -> základ používanej pozičnej sústavy (pre ASCII r=128 / r = 256)
	- $l,a$ -> niektoré malé prirodzené čísla 

##### Multiplikácia
Výber $m$ nie je jej kritickým článkom, zvyčajne je to mocnina 2

**Metóda**:
- vypočítame desatinnú časť súčinu $k*A$, kde $A$ je konštanta ($A\epsilon R^+$)
- výsledok sa vynásobí $m$, nájde sa celé číslo neprevyšujúce získanú hodnotu

Výber hodnoty $A$ -> zvykne sa používať obrátená hodnota **zlatého rezu**

#### Riešenie kolízií
Nie je možné vylúčiť možnosť kolízie.

**Kolízia** nastáva ak dostaneme rovnaký výsledok z hashovacej funkcie z viacerých kľúčov

##### Separátne reťazenie
Ide o najjednoduchšiu stratégiu.
Dva kľúče s rovnakou hodnotou sú umiestnené v rovnakom zozname za sebou.

##### Otvorené adresovanie
Samotná tabuľka pozostáva z prvkov hashovacej množiny, namiesto zoznamov a smerníkov.
Pri ukladaní nového prvku sa hľadá prvá vhodná neobsadená pozícia.

Odstránenie prvku je zložitejšie, pretože nám môže zaberať miesto, na ktorom nič už nie je => potrebujeme používať **flags**, aby sme vedeli či je prázdna alebo nie.

Generovanie postupnosti indexov:
- Pri INSERT -> testovanie obsadenosti pozícií
- Pri MEMBER/DELETE -> dokým nenájdeme našu položku

##### Zaradenie prvku do tabuľky
**Prístupy**:
- **Lineárne testovanie**
	- interval medzi dvoma testami je konštantný
	- nastáva problém **zhlukovania**
- **Kvadratické testovanie**
	- interval sa zvyšuje lineárne
- **Dvojite hašovanie**
	- interval medzi testami je vypočítaný pomocou ďalšej hašovacej funkcie