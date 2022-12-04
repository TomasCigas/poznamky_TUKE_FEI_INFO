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
Základom *cleanroom* je správna implementácia modelu do kódu. Pokiaľ sa v modelovacej časti nenachádza chyba, tak pri programovaní už by nemala vzniknúť žiadna.
Výhodou cleanroom, je že ešte pred vytváraním kódu vieme jeho presnú štruktúru, teda dokážeme automatizovať tvorbu kostry kódu.

*Cleanroom* - "najčistejší" spôsob tvorby programu, pretože eliminuje chyby ešte pred kódením.
![[Pasted image 20221204140603.png]]

# Špirálový model
[[COCOMO#COCOMO II|COCOMO II]] je založený na špirálovom modely. Integruje správu a kontrolu chýb, prípadne rizík, ktoré môžu vznikať počas tvorby projektu.

![[Pasted image 20221204140732.png]]

Jedná sa o iteratívny spôsob tvorby systému/programu. Vraví taktiež o kumulatívnom náraste zdrojov a času pri tvorbe projektu. Narozdiel od [[#Vodopádový model|vodopádového modelu]] môže byť (teoreticky) špirálový model používaný do nekonečna.

# V-model
Sústredí sa na testovanie celého projektu, čím zabezpečuje jeho kvalitu + si všetky podklady pripravíme dopredu, pri čom to overíme zákazníkom. 

![[Pasted image 20221204141046.png]]

# SCRUM
SCRUM je najzákladnejší agílny model, od ktorého sa väčšina odvíja. Je opaku cleanroom, teda problém sa snažíme prispôsobiť našemu riešeniu, teda snažíme sa šablónovo riešiť hocijaký problém. Takéto riešenie je veľmi rýchle, avšak veľmi neflexibílne.

V tíme vystupuje tzv. *scrum-master*, ktorý rieši konflikty, resp. problémy, ktoré môžu počas vývoja vznikať. Najideálnejšie sa im snaží predchádzať.
Každý deň sa vykonáva krátky meeting, kde sa všetci zíjdu, nevytvárajú kód, ale synchronizujú svoju prácu -> môže vznikať problém pri veľkom počte ľudí.

Koncept **SCRUMu**:
![[Pasted image 20221204141548.png]]

Model jedného **šprintu**:
![[Pasted image 20221204141615.png]]

# RAD
**R**apid **A**pp **D**evelopment je model, ktorý sa viac sústredí na prototypovanie a rýchly feedback od zákazníka, pri čom plánuje len veľmi zľahko. Toto zabezpečuje rýchly a kvalitný finálny produkt. Umožňuje nám pridávať alebo meniť funkcie počas iterovania bez toho, aby sme museli začínať od začiatku (keďže stále žiadame feedback).

![[Pasted image 20221204141935.png]]

# DSDM
**D**ynamic **S**ystem **D**evelopment **M**ethod je model, ktorý vychádza z myšlienky použiteľnosti.
Snažíme sa predikovať budúcnosť a začať vývoj ešte pred tým, než je náš produkt použiteľný (možno kvôli prostrediu, alebo zdrojom).

![[Pasted image 20221204142152.png]]
