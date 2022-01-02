# Typy plánovania
## Krátkodobé plánovanie
Určuje, ktorý [[Procesy|proces]] bude pokračovať na procesor.

Aktivuje sa ak sa vyskytne udalosť, ktorá:
- zablokuje bežiaci proces
- poskytuje príležitosť prevziať  procesor od bežiaceho procesu ([[Prerušenia|prerušenie]])

Charakteristiky:
- najdôležitejšie plánovanie
- často vykonávané
- krátka časová zložitosť

Cieľ je alokovať procesor tak, aby sa optimalizovala funkčnosť [[#Kritéria správania|kritérií správania]] systému:

### Kritéria správania
Jednotlivé kritériá môžu byť prepojené nepriamou úmernosťou => sú protichodné (napr. [[#Predvídavosť]] - [[#Priepustnosť]])

#### Používateľsky orientované
- rýchlosť spracovania procesu

##### Predvídavosť
- zabezpečenie aby každý proces zaberal podobné množstvo zdrojov a času nehľade na vypätie systému

#### Systémovo orientované
- využitie systémových zdrojov (CPU, [[Vstupno výstupné zariadenia|V/V]] ...)

##### Ohľaduplnosť (Fairness)
- zabezpečenie, aby nedošlo k [[Pojmy IPC#Vyhladovanie Starvation|vyhladovaniu]]

##### Uplatnenie priorít
- zabezpečenie vykonania prioritných procesov
![[process_priority.excalidraw]]

##### Balancovanie využitia zdrojov
- zaneprázdnenie systémových zdrojov

#### Výkonnostne orientované
- výkon systému

##### Systém
###### Priepustnosť
- počet splnených úloh procesorom

###### Využitie procesora
- percento času využitia procesora

##### Používateľ
###### Doba odozvy
- zabezpečenie požadovanej odozvy od procesora
- dôležité pre interaktívne programy

###### Čas otočenia
- interval v ktorom je proces odložený a v ktorom beží

###### Deadline
- špecifikovanie ukončenia procesu

### Algoritmy

## Strednodobé plánovanie
Jedná sa o stratégie [[Virtuálna pamäť#Výmena stránok Replacement policy|zámeny stránok]].

## Dlhodobé plánovanie
Určuje prrogram, ktorý bude zaradený do systému.

Určuje mieru multiprogramovania

Pre interaktívne programy -> moment prihlásenia
- dlhodobé plánovanie je oklieštené a tieto procesy sa posúvajú rovno do [[#Krátkodobé plánovanie|krátkodobého plánovania]]

Stratégie:
### FCFS (First Come First Served)
- Prvý príde, prvý bude obslúžený

### Prostriedky regulácie výkonnosti systému
- limitujeme počet procesov, alebo niektoré procesy zakazujeme (?)

## Vstupno/Výstupné plánovanie
