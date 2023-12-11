***********
Náš algoritmus sa uči prostredníctvom **označeného data setu**.

Rozdelenie:
- **Klasifikácia**
	- hodnota, ktorú predikujeme má konečný počet značiek (variácií)
	- teda rozdeľujeme vstupy podľa značiek a algoritmus 
- **Regresná analýza**
	- počet značiek nie je konečný
	- obvykle ide o reálne číslo (teda počet je nekonečný)

# Klasifikácia
## Perceptron
Ide o najjednoduchší typ neurónovej siete. Rozďeľuje všetky dáta lineárne podľa svojich váh vstupných dát **x** a intérnych váh **w**, ktoré sa učí (spolu volané ako **z**) získa výslednú klasifikačnú hodnotu **y**. 
Algoritmus je jednoduchá krokovacia funkcia, ktorá závisí len na učení intérnych váh:
1. Inicializujeme w = 0 alebo ~0
2. Pre každú vzorku
	1. výpočet y'
	2. aktualizujeme $w_j=w_j + \Delta w$, kde $\Delta w = \eta (y^{i} - y^{-i})*x_j^{i}$ a $\eta$ je hyperparameter váhy učenia
	3. opakujeme dokedy máme vzorky/do istého počtu
Hlavnou myšlienkou perceptronu je minimalizácia chyby.

## Metóda podporných vektorov (SVM)
V prípade klasifikácie sa označujú aj ako **SVC**.
Ide o rozšírenie [[#Perceptron|perceptronu]], v tomto prípade sa minimalizuje hraničné pásmo namiesto chyby. Je výpočtovo náročnejšie ako perceptron, ale taktiež presnejšie.

V prípade, že sa nedá riešenie získať lineárne používame slack (voľný) [[Terminológia a označenia v ISI|hyperparameter]], krorý nám povoľuje istú mieru chybného riešenia (obvykle sa nazýva **C**).
Ďalším spôsobom je kernelizácia, kde prechádzame do vyššej roviny, pri čom nechávame rovnaký počet parametrov.

## Rozhodovacie stromy
Jedná sa o vytvorenie stromu, ktorého uzly sú jednotlivé "rozhodnutia" stromu a listy sú výsledné kategórie.
Dobre zvládajú zmiešané a kategórické atribúty. Avšak ide tu o veľkú hrozbu pretrénovania.

Ako [[Terminológia a označenia v ISI|hyperparametre]] tu vystupujú počty detí uzla a maximálna hĺbka.

Nie je ovplyvnený [[Inteligentné systémy v informatike#Predpsracovanie dát|škálovaním]].

## Náhodné lesy
Jedná sa o skupinový klasifikátor. Jednoducho povedané jedná sa o viacero [[#Rozhodovacie stromy|stromov]], medzi ktorými sa následne vyberá rôznym spôsobom. Napr. hlasovaním.

Obmedzuje to pre/podtrénovanie jedného stromu. [[Terminológia a označenia v ISI|Hyperparametre]] sú rovnaké ako pri [[#Rozhodovacie stromy|stromoch]] + ich počet a forma rozhodovania.

## K najbližších susedov
Relatívne lenivý prístup k riešeniu. Algoritmus sa pozrie na svoj radius a rozhodne sa podľa toho, koľko susedov toho istého typu sa nachádza v jeho okolí.
Problémom je dimenzionalita, s narastajúcim počtom parametrov a atribútov narastá aj jeho výpočtová rýchlosť. Taktiež je senzitívny na [[Inteligentné systémy v informatike#Predpsracovanie dát|škálovanie]].

Ako [[Terminológia a označenia v ISI|hyperparametre]] máme radius bodu a počet požadovaných susedov.

## Základné klasifikátory s najlepšími výsledkami
- XGboost (podobný [[#Náhodné stromy|náhodným lesom]])
- TabNet (neurónové siete)

# Regresná analýza
**Používajú sa**:
- [[#Rozhodovacie stromy]]
- [[#Náhodné lesy]]
- [[#Metóda podporných vektorov (SVM)]] (napr. metóda najmenších štvorcov)
- a i.
