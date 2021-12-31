# Virtuálna pamäť
**Virtuálna pamäť** *je označenie pre špecifickú techniku [[Správa pamäte|správy pamäte]]* v [[Klasifikácie#Počtu paralelne bežiacich úloh|multitaskových]] [[Operačné systémy|operačných systémoch]].

Vyžaduje si podporu hardvéru a softvéru.


Vďaka nej môžu mať aplikácie (zdánlivo) prístup k celému adresnému priestoru, ako k [[Fyzická pamäť|fyzickej pamäti]], tak aj k dátam uloženým na disku. Teda procesy majú k dispozícii väčšie množstvo pamäte ako sa na počítači nachádza

Virtuálna pamäť zvykne byť implementovaná pomocou:
- [[Historické prístupy#Stránkovanie|Stránkovania]]
- [[Historické prístupy#Segmentácia|Segmentácie]]

Maximálna veľkosť virtuálnej pamäte pre OS o veľkosti:
- 32 bitov -> 4 GiB
- 64 bitov -> 16 EiB

Koncept virtuálnej pamäte zahŕňa odelenie logickej pamäte (ako ju vnímajú používatelia) od fyzickej pamäte.

Pokiaľ sa proces odkazuje na pamäť, ktorá nie je fyzicky prítomná v opračnej pamäti nastáva [[Prerušenia|prerušenie]] a operačný systém sa snaží nájsť údaj ktorý je hľadaný v [[Pamäť#Hierarchia pamätí|sekundárnej pamäti]].

## Princíp virtuálnej pamäte
- Všetky adresy v rámci procesu sú logické
- [[Pojmy pamäť#Logická adresa|Logické adresy]] sú transformované na [[Pojmy pamäť#Fyzická adresa|fyzické adresy]]
- Pamäť procesu nemusí byť súvisle uložená v oblasti fyzickej pamäte

## Dôsledok virtuálnej pamäte
- Nie všetky stránky/segmenty pamäte sa musia nachádzať v [[Pamäť#Hierarchia pamätí|operačnej pamäti]]
- Umožňuje fungovania viacerých procesov v operačný systém
- Proces môže mať viac pridelenej pamäte ako operačný systém

## Princíp lokálnosti
- Základný princíp, na ktorom je postavená virtuálna pamäť
	- Inštrukcie
	- Dáta
- Nie vždy sa uplatní:
	- [[Objektovo orientované programovanie|OOP]]
	- vlákna

## Hardverová podpora

**Implementácia** :

![[virtual_mem.excalidraw]]
- bez [[Ochrana pamäte|ochranných prostriedkov]]

### Tabuľka stránok
- Pri 32-bitovej adrese je 4KB (12 bitov) stránka označená 20 bitovým číslom -> tabuľka je väčšia ako operačná pamäť

Riešenie:
#### Viacúrovňová štruktúra tabuľky stránok
![[layered_virtual_mem.excalidraw]]
- tabuliek môže byť viacero pri 64-bitovej adrese
#### Obrátená štruktúra tabuľky
![[vm_inverted_page.excalidraw]]
(zjednodušene)
- reťazenie stránok môže zdĺžiť
#### Vyhľadávanie podľa obsahu (TLB)

## Softvérová podpora
Musí obsahovať:
### Postup získavania (Fetch policy)
Rozhoduje kedy preniesť stránku do operačnej pamäte

### Vyžiadanie stránkovania (Demand paging)
- Stránkovanie na **požiadanie**
- Môže byť pomalé kvôli zapisovania a čítania zo [[Pamäť#Hierarchia pamätí|sekundárnej pamäte]]
### Predstránkovanie (Prepaging)
- Odhaduje ktorá stránka sa bude používať a pripravý sa pred použitím

### Umiestňovanie stránok (Placement policy)
- Kde sa umiestňujú stránky v **operačnej a fyzickej pamäti**
- [[Historické prístupy#Stránkovanie|Stránkovanie]] je bezproblémové vďaka rovnakej veľkosti stránok

### Výmena stránok (Replacement policy)
- Určenie ktorá stránka bude vybraná na **výmenu obsahu**
- **Frame locking** -> uzamknutie stránok, ktoré obsahujú dôležité dáta/kód aby sa tieto stránky nevymieňali
- Hlavné algoritmy:
#### Optimálny
- Vyberie stránku, ktorá sa v najbližšej dobe nebude využívať (ideálne vôbec)
- Spôsobuje najmenší výpadok stránok
- Nedá sa implementovať :)
- Slúži ako ideálna hranica

#### Najmenej používané (Least recently used -> LRU)
- Vymeňí stránku, ktorá bola najdlhšie nepoužitá
- Prakticky neimplementovateľný, pretože by sme ku každej stránke pridať čas poslednej manipulácie -> extrémne zväčšuje jej veľkosť + musíme prehľadávať stránky aby sme vybrali ten ideálny

#### Prvé-dnu-prvé-von (First-in-first-out -> FIFO)
- Najjednoduchšia implementácia
- Vymení stránku ktorá bola v pamäti najdlhšie (ktorá prišla ako prvá)
- Má zlé výsledky

#### Hodiny
- Zo stránok si vytvoríme kruhový zoznam (hodiny) a so smerníkom (ručička) ukazujeme na poslednú prezeranú stránku v zozname. Taktiež máme uložený zoznam použitia stránok, ktorý slúži na vyberanie vhodnej stránky
- Pokiaľ neexistuje voľná stránka kontroluje naša ručička či boli stránky použité, pokiaľ:
	- áno -> tak jej nastavujeme že nebola použitá
	- nie -> vymieňa sa stránka a nastavujeme, že bola použitá
	- ručička sa posúva ďalej v oboch prípadoch

### Vyrovnávanie stránok (Page buffering)
#add_info

### Manažovanie rezidentnej skupiny (Resident Set Managment -> RS managment)
- Veľkosť RS:
	- Fixná
	- Variabílna
- Škála presúvania
	- Globálna
	- Lokálna

### Postup čistenia (Cleaning policy)
- Požiadavka
- Predčisteni

### Controla načítania (Load control)
- Stupeň multiprogramingu