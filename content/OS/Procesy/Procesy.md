# Procesy

**Proces** je abstrakcia operačného systému, ktorá reprezentuje všetko, čo je potrebné prebeh [[#Program|programu]].

[[Operačné systémy|Operačný systém]] si musí udržiavať informácie o svojich zdrojoch aby ich mohol poskytnúť procesom, toto sa nazýva **kontrolné tabuľky**.
![[control_table.excalidraw]]

Operačný systém taktiež rozďeľuje jednotlivé procesy do troch skupín:
- Bežiace
- Pripravené
- Blokované

OS musí taktiež vedieť **lokáciu** a **informácie** procesu, aby ho mohol spravovať a riadiť, na čo sa teda využíva [[#Riadiaci blok procesu|PCB]].

_Fyzická reprezentácia procesu je jeho umiestnenie v pamäti -> program._

## Riadiaci blok procesu
V **PCB** sa ukladajú _atribúty_, ktoré určujú jeho [[#Identifikáciu|identifikáciu]], [[#Stav|stav]] a [[#Riadenie|riadenie]].

Grafická reprezentácia:
![[PCB.excalidraw]]

### Identifikáciu
Jedná sa o **numerické** identifikátory, ktoré môžu reprezentovať:
- identifikátor tohto procesu
- identifikátor rodičovského procesu
- používateľ procesu
- a i.

### Stav
Ide o registre obsahujúce stavy a rôzne dáta procesu.

### Riadenie
Obsahuje informácie potrebné na riadenie a zmenu stavu procesu. Ide o napr.:
- Prioritu procesu
- Informácie o plánovaní
- Udalosti

## Program
**Program** je v informatickom zmysle nejaká postupnosť inštrukcií, ktorá je zapísaná v kóde, ktorému počítač rozumie a dokáže ich vykonať.

### Porovnanie programu a procesu
Porovnanie|Program|Proces
------|----|-----
Popis|Postupnosť inštrukcií|Spustený program
Správanie|Pasívne|Aktívne
Dĺžka života|Dlhá|Limitovaná
Potrebné zdroje|Súbor na disku (1)|CPU, pamäť, adresa (mnoho)


---
- [[Život procesov]]
- [[Zdieľanie času a zdrojov]]
- [[Stavy procesov]]
- [[Prepínanie procesov]]
---