# Plánovanie diskových operácií

- Parametre disku (HDD):
![[HDD_params.excalidraw]]

Je potrebné implementovať plánovanie diskových operácií a spôsoby čítania a zapisovania dát na/z disku, pretože náhodné čítanie môže zaberať veľa času. (?) => Je potrebné zaoberať sa spôsobmi ako zlpešiť "výkonnosť" disku -> posunúť ju čo najviac od **náhodného čítania** k **sekvenčnému čítaniu**.

## Algoritmy čítania
Pre čítanie stôp:
55, 58, 39, 18, 90, 160, 150, 38, 184
### FCFS
Prvý príde, prvý bude spracovaný
 ![[FCFS.png]]
 
### Shortest Service Time First (SSFT)
Vyberá požiadavku, ktorá znamená najmenší pohyb hlavičky.
![[SSFT.png]]
Môže dôjsť k [[Pojmy IPC#Vyhladovanie Starvation|vyhladovaniu]].

### SCAN
Hlavička sa pohybuje od minimálnych k maximálnym a obsluhuje požiadavku až keď sa k nej dostane.
![[SCAN.png]]

- avšak ošetrujeme požiadavky, ktoré sú bližšie k maximu/minimu v kratších intervaloch -> preferuje "okrajové" stopy a posledné požiadavky
- zhoršuje efektivitu, ale zlepšuje [[Pojmy IPC#Vyhladovanie Starvation|vyhladovanie]].

### C-SCAN
(Circular SCAN)

Modifikácia [[#SCAN]], ktorá číta len keď sa hlavička hýbe v jednom smere.
![[C-SCAN.png]]

### Ďalšie algoritmy
- **N-step-SCAN**
	- máme N podfrontov
	- obsluhuje sa jednotlivé fronty
- **FSCAN**
	- Máme 2 podfronty
	- jeden sa zaberá a druhý sa zapĺňa

## Algoritmy plánovania
![[planning_algors.png]]