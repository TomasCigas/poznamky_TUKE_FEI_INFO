# Algoritmy plánovania
X|FCFS|Round Robin|SPN|SRT|HRRN|Feedback
---|---|---|---|---|---|---
**Funkcia**|$max[w]$|konštantá|$min[s]$|$min[s-e]$|$max(\frac{w+s}{s})$|[[#Feedback\|špeciálne]]
**[[Plánovanie procesov#Spôsob rozhodovania Decision mode\|Rozhodovanie]]**|Nepreem.|Preem. (časovo kvantované)|Nepreem.|Preemp. (pri príchode)|Nepreem.|Preem. (časovo kvantované)
**[[Typy plánovania#Priepustnosť\|Priepustnosť]]**|Nezávislé|Môže byť nízka ~ kvantá|Vysoká|Vysoká|Vysoká|Nezávislé
**[[Typy plánovania#Doba odozvy\|Odozva]]**|[[#FCFS First Come First Serve\|Môže byť vysoká]]|Dobrá pre krátke procesy|Dobrá|Dobrá|Nezávislé
**Overhead**|Minimálny|Minimálny|Môže byť vysoká|Môže byť vysoká|Môže byť vysoká|Môže byť vysoká
**Efekt na procesy**|Penalizuje krátke procesy|[[Typy plánovania#Ohľaduplnosť Fairness\|spravodilivosť]]|Penalizuje dlhé procesy|Penalizuje dlhé procesy|Dobrý balanc|Môže prioritizovať V/V procesy
**[[Pojmy IPC#Vyhladovanie Starvation\|Vyhladovanie]]**|Nie|Nie|Možné|Možné|Nie|Možné

**Kvantum** ($q$) -> množstvo času, ktoré sa priradí jednému procesu.

## FCFS (First Come First Serve)
Prvý príde, prvý bude obslúžený.

Môže mať vysokú odozvu pri vysoko rozlišnej dobe spracovania procesov.

Charakteristiky:
- najjednoduchši
- neefektívne na uniprocesorových systémoch

## Cyklický (Round Robin)
Funguje na základe časovača (časové kvantá) .
Pri výskyte prerušenia ide bežiaci proces do frontu a ďalší sa vyberá zvyčajne na základe [[#FCFS First Come First Serve|FCFS]].

Časové kvantum nesmie byť príliš veľké, ale musí byť o trochu väčšie ako je typický čas interakcie (funkcie procesora).

Je efektívny pre transakčné systémy a systémy zdieľania času.

## SPN (Shortest Process Next)
Proces s najmenším časom na vypracovanie bude pokračovať.

Problém implementácie je vedieť, resp. odhadnút čas do ukončenia procesu.

Nie je vhodný pre transakčné systémy a systémy zdieľania času.


## SRT (Shortest Remaining Time)
Proces s najkratším ostávajúcim časom na dokončenie bude následovať.

Je to preemptívny variant [[#SPN Shortest Process Next|SPN]].


## HRRN (Highest Response Ratio Next)
Funguje na základe toho, ako dlho proces čaká a ako dlho trvá jeho výpočet

Nasledovať bude ďalší proces, kde:
$$
max(\frac{w+s}{s})
$$
[[Život procesov#Vykonanie programu|(w,s)]]

## Feedback
Penalizuje procesy, ktoré bežia dlhšie na základe **mechanizmu dynamických priorít**:
![[dynamic_priority.excalidraw]]
- jednotlivé fronty sú obvykle [[#FCFS First Come First Serve|FCFS]]

## "Traditional UNIX"
Zabezpečuje dobrú odozvu pre ineraktívne procesy a nespôsobuje [[Pojmy IPC#Vyhladovanie Starvation|vyhladovanie]] nízko prioritných procesov.

Funguje na základe viacúrovňového [[#Feedback|feedback]] algoritmu, kde každý front využíva [[#FCFS First Come First Serve|FCFS]].

Priority sa prepočítavajú každú sekundu.