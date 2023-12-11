***********
# Cowboy coding
Veľmi jednoduchý a aj prvý spôsob vytvárania programu:
![[cowboy_coding]]

# Vodopádový model
Snaha o vytvorenie komplexnejšieho modelu na väčšie projekty. Nebol zaužívaný, nakoľko nebol dostatočne detailný, pri nájdení chyby v neskoršom štádiu by sme museli začať od začiatku

![[Pasted image 20221204131559.png]]

# Vylepšený vodopádový model
Vylepšenie [[#Vodopádový model|vodopádový model]], avšak stále nie je ideálny na tvorbu veľkých a zložitých projektov, najmä v OOP.
![[Pasted image 20221204131746.png]]

# Zjednotený proces
Zjednotený proces (UP) je vylepšenie [[#Vylepšený vodopádový model|WM-I]] o OOP funkcionality vďaka integrácii UML diagramov do plánovania:
![[Pasted image 20221204131922.png]]

UP taktiež rozpráva o rozložení času a zdrojov pre jednotlivé časti projektu:
![[Pasted image 20221204135652.png]]

- Inception = Analýza
- Elaboration = Špecifikácia
	- ?Môže klesať efektivita, kvôli zlému manažmentu ľudských zdrojov
- Construction = Dizajn, kódenie a testovanie
- Transition = Integrácia

Existuje viacero verzií UP, resp. [[#RADIT|RADITu]], poďla potreby (Agile, Basic, Enterprise, Rational Open a i.):
- **Agile**
	- vopred vieme koľko iterácií budeme mať prípadne aké budú, avšak sú pozmeniteľné
	- dokážeme meniť poradie iterácií podľa potreby
	- má problémy s veľkými projektami

## RADIT
Označenie krokov, ktoré musíme vykonať pri každom kroku testovania.

# Cleanroom
*Cleanroom* - "najčistejší" spôsob tvorby programu, pretože eliminuje chyby ešte pred kódením.

Základom *cleanroom* je správna implementácia modelu do kódu. Pokiaľ sa v modelovacej časti nenachádza chyba, tak pri programovaní už by nemala vzniknúť žiadna.
Výhodou cleanroom, je že ešte pred vytváraním kódu vieme jeho presnú štruktúru, teda dokážeme automatizovať tvorbu kostry kódu.

Záleží na otázke manažmentu, či použiť cleanroom, alebo agilný spôsob:
- Vytváranie už podobného projektu: *Agílne*
- Vytváranie nového/neznámeho projekti: *Cleanroom*

Podobá sa vodopádovému modelu, avšak je rozdelený na 2 časti:
![[Pasted image 20221204140603.png]]

# Špirálový model
[[COCOMO#COCOMO II|COCOMO II]] je založený na špirálovom modely. Integruje správu a kontrolu chýb, prípadne rizík, ktoré môžu vznikať počas tvorby projektu.

![[Pasted image 20221204140732.png]]

Jedná sa o iteratívny spôsob tvorby systému/programu. Vraví taktiež o kumulatívnom náraste zdrojov a času pri tvorbe projektu. Narozdiel od [[#Vodopádový model|vodopádového modelu]] môže byť (teoreticky) špirálový model používaný do nekonečna.

# V-model
Sústredí sa na testovanie celého projektu, čím zabezpečuje jeho kvalitu + si všetky podklady pripravíme dopredu, pri čom to overíme zákazníkom. 

![[Pasted image 20221204141046.png]]

# SCRUM
SCRUM je najzákladnejší agílny model, od ktorého sa väčšina odvíja. Je opaku [[#Cleanroom|cleanroom]], teda problém sa snažíme prispôsobiť našemu riešeniu, teda snažíme sa šablónovo riešiť hocijaký problém. Takéto riešenie je veľmi rýchle, avšak veľmi neflexibílne.

V tíme vystupuje tzv. *scrum-master*, ktorý rieši konflikty, resp. problémy, ktoré môžu počas vývoja vznikať. Najideálnejšie sa im snaží predchádzať. Mal by byť informovaný a relatívne zasadený vo všetkých taskoch šprintu.

Každý deň sa vykonáva krátky meeting, kde sa všetci zíjdu, nevytvárajú kód, ale synchronizujú svoju prácu -> môže vznikať problém pri veľkom počte ľudí.

Koncept **SCRUMu**:
![[Pasted image 20221204141548.png]]

Model jedného **šprintu**:
![[Pasted image 20221204141615.png]]

Väčšina tímov adaptuje svoj SCRUM model, nakoľko ignoruje veľké množstvo problémov. Ako napríklad zlú terminológiu.

## DAD
**D**isciplined **A**gile **D**elivery je škálovateľná forma [[#SCRUM|SCRUMu]], ktorá berie do úvahu risky a je *enterprise-vedomí*.
Mení pohľad na projekt z vývojára na *zákazníka*, teda nesnažíme sa dodať predateľný SW, ale akceptovateľné riešenie, ktoré zákazník vyžaduje.
Preto je aj terminológia bližšia zákazníkovi.

Model DAD s pridaním R/T grafu z [[#Zjednotený proces|UPu]]
![[Pasted image 20221204191718.png]]

### Ciele organizácie
Zdieľame informácie (hlavne, či niekto nerobí na rovnakom probléme osobitne), nikto nesmie pracovať na tasku sám, inak bude mať limitovaný pohľad na projekt (ideálne preberáme už spracovanú robotu). Pri nedostatku komunikácii dochádza k vytváraniu chýb v kóde.
Zdieľame informácie aj medzi lokáciami:
- ideálne fyzicky (ak sa dá)
- pri veľkých firmách (lokáciách) používame ambasádorov

### Team awarness
![[Pasted image 20221204192431.png]]



### V skratke
1. Zameriavame sa na konzúmne riešenia, nie len predateľný softvér
2. Predĺžime SCRUMovú konštrukciu aby sme mohli opísať *celý* životný priebeh SW + poslanie (SCRUM je dobrý začiatok, ale treba škálovať)
3. Posunieme sa z označovania metód (zľudšujeme terminológiu)
4. Adoptujeme explicitné stratégie na kontrolu
5. Zameriavame sa na ciele aby sme umožnili škálovateľnosť

## Water-SCRUM-fall
Hovadina, nerobiť. Príliš zložité začiatočné a konečné fázy projektu.

# RAD
**R**apid **A**pp **D**evelopment je model, ktorý sa viac sústredí na prototypovanie a rýchly feedback od zákazníka, pri čom plánuje len veľmi zľahko. Toto zabezpečuje rýchly a kvalitný finálny produkt. Umožňuje nám pridávať alebo meniť funkcie počas iterovania bez toho, aby sme museli začínať od začiatku (keďže stále žiadame feedback).

![[Pasted image 20221204141935.png]]

# DSDM
**D**ynamic **S**ystem **D**evelopment **M**ethod je model, ktorý vychádza z myšlienky použiteľnosti.
Snažíme sa predikovať budúcnosť a začať vývoj ešte pred tým, než je náš produkt použiteľný (možno kvôli prostrediu, alebo zdrojom).

![[Pasted image 20221204142152.png]]

# Ostatné agílne metódy
- FDD (Feature)
- TDD (Test)
- XP (Extreme)
- BDD (Behaviour)
- DDD (Domain)

# Prototypovanie

**Typ:**
- *Vertikálny*: rozvoj prototypu k finálnemu projektu (dokončovanie existujúcich funkcií).
- *Horizontálny*: zisťujeme a skúšame všetky funkcionality, ktoré sa môžu v programe nachádzať.


## Na odhodenie
Účelne vytvorený len na zistenie požiadaviek a feedbacku, ale ani jedna časť z toho sa nebude nachádzať vo finálnom programe
## Evolučný
Obsahuje všetko potrebné na funkciu a len evolučne prehlbujeme už existujúce funkcie
## Inkrementačný
Postupujeme podľa toho, čo zákazník potrebuje a požaduje
## Extrémny
Prototyp sa blíži ku finálnemu projektu a ideálne ho len už podľa zákazníka upavíme, aby spĺňal všetky požiadavky.

# Lean Development
Redukcia [[#SCRUM|SCRUMu]] o scrum-mastera, keďže všetci vedia, čo majú robiť a review so synchronizáciou robia navzájom.