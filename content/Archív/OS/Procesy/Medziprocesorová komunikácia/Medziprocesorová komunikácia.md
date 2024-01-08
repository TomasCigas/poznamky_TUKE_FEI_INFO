# Medziprocesorová komunikácia
(IPC)

Povoľuje komunikáciu a synchronizáciu medzi kooperujúcimi [[Procesy|procesmi]].

Spôsoby komunikácie a synchronizácie v UNIXových systémoch sa nachádza [[IPC|tu]].

! Je veľmi ťažké odhaľovať chyby medzi kooperujúcimi procesmi !

**Dijkstra** -> rozpracoval efektívny a spoľahlivý mechanizmus pre podporu kooperácie

## Spôsoby interakcie procesov
Úroveň spolupráce s inými procesmi|Vzťah
--------|------
Nezávislé procesy|Vzájomná súťaž o zdroje
Nepriamo spolupracujúce procesy|Kooperácia procesov zdieľaním zdrojov
Priamo spolupracujúce procesy|Kooperácia procesov komunikáciou

### Súťaženie o zdroje
- Viac procesov chce prístup k rovnakému zdroju
- Neexistuje medzi nimi žiadna komunikácia
- Dôsledky:
	- [[Pojmy IPC#Deadlock uviaznutie|Deadlock]]
	- [[Pojmy IPC#Vyhladovanie|Vyhladovanie]]
	- Nekorektná činnosť
- Riešenie dôsledkov -> [[Pojmy IPC#Vzájomné vylúčenie Mutual exclusion|vzájomné vylúčenie]]

### Kooperácia prostredníctvom zdieľania
- Procesy navzájom nekomunikujú, avšak musia kooperovať aby nedošlo k [[#Súťaženie o zdroje|súťaženiu o zdroje]]
- Potrebujú **riadiaci mechanizmus**, ktorý bude zabezpečovať **integritu dát**

- Tento systém funguje pokiaľ máme rozdelené dva procesy na mód čítania a zápisu
	- Avšak pri večšom počte procesov môže dochádzať k rovnakým problémom ako pri [[#Súťaženie o zdroje|súťažení o zdroje]], najmä v prípade zápisu

#### Technická podpora
Spôsoby vyriešenia:

##### Zákaz prerušenia
- zakázanie [[Prerušenia|prerušenia]] umožní procesu vykonať [[Pojmy IPC#Kritická sekcia|krticikú sekciu ]] bez toho aby mal ku kritickému zdroju prístup iný proces
- platí len pre uniprocesor a zakázanie prerušenia je privilegovaná inštrukcia -> nie je realizovatelné

##### Špeciálne inštrukcie
-  Princíp "Test and Set" -> opakovane kontrolujeme či môžeme pokračovať v kritcikej sekcii a pokiaľ áno, tak ju vykonáme a potom oznámime, že sme z nej už vyšli
-  [[Pojmy IPC#Atomická operácia|Atomická operácia]]
	-  Princíp "Compare&Swap" -> porovnávame, či sa v pamäti nachádza *testovacia* premenná a pokiaľ áno nastavíme hodnotu uloženú v pamäti na *novú hodnotu*
		Použiva sa v [[Semafóry|semaforoch]] či Mutexoch
	 - Princíp "Exchange instruction" -> výmena obsah registra a pamäte
		
## Dizajnové charakteristiky pre [[Synchronizácia|synchronizáciu]] a [[Komunikácia|komunikáciu]]

### Synchronizácia
- príjmateľ nemôže prijať správu, kým nie je odoslaná


### Posielanie
- Blokujúce
	- proces je zablokovaný, kým nebude správa prijatá
- Neblokujúce
	- proces nie je zablokovaný a pokračuje v nejakej činnosti (obvykle generovanie ďalších správ)

### Príjmanie
- Blokujúce
	- zablokovanie, kým nedojde správa
- Neblokujúce
	- spracovanie "nepríchodu" správy
- Testovanie na príchode

### Adresácia
Spôsob špecifikácie ktorý proces dostane správu

- **Priama** -> špecifikuje presného adresáta
	- Poslanie
	- Prijatie
		- explicitné 
		- implicitné

- **Nepriama** -> použitie schránky
	- statická
	- dynamická
	- vlastníctvo

### Formát
Závisí od účelu navrhnutého systému

- **Obsah**
- **Dĺžka**
	- *fixná* -> jednoduchá implementácia
	- *variabilná* -> flexibílnejšie
		- fixná hlavička
		- premenlivé telo

### Disciplína frontovania
- **FIFO** -> prvá príde prvá odíde (podobné ako [[Virtuálna pamäť#Prvé-dnu-prvé-von First-in-first-out - FIFO|tu]])
- **Prioritné**



---
- [[Pojmy IPC]]
- [[Komunikácia]]
- [[Synchronizácia]]
---