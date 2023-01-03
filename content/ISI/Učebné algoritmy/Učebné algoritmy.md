***********
Učebné algoritmy s rôznymi požiadavkami a postupmi.

# Metódy evaluácie modelov a ladenia hyperparametrov
Ladením hyperparametrov dosahujeme lepšie výsledky z našich modelov.

Obvykle ladíme:
- Iteračne
- Random
- Zmiešane

pri ladení môže dôjsť ku *overfitovaniu* (pretrénovaniu) modelu, tomuto predchádzame *validáciou modelu*:
- **Hold-Out** - rozdelíme dáta na 3 sady (trénovacie, validačné a testovacie), kde túnujeme model len na dvoch z nich a potom testujeme s tretím
- **Cross-validation** - dáta rozdelíme na $n$ častí a trénujem model $n$-krát.
	- vystupuje tu k-fold parameter, ktorý hovorí na koľko častí rozdelíme dáta
	- *strutified k-fold*: k-fold = počtu dát
- **Diagnostika pomocou kriviek učenia a validácie** - krivky nám ukazujú, či sme mdel pod/pretrénovali
	- ![[krivky_diagnost.excalidraw]]
	- kde plnou čiarou sú reálne výsledky testovania a čiarkovanou zdánlivé krivky validácie

**Riešenie pod/pretrénovania**:
- *Podtrénovanie* - pridať atribúty, spresniť hyperparametre
- *Pretrénovanie* - pridať vzorky, zjemniť hyperparametre, odobrať atribúty

**Metriky pre evaluáciu výkonnosti**:

*Matica zámien* nám určuje aký druh chyby náš model zrobil
![[matica_zamien.excalidraw]]

# Redukcia dimenzionality
**Redukcia [[Terminológia a označenia v ISI|dimenzionality]]** -  jedná sa o redukciu počtu vzoriek, za účelom zlepšenia, alebo zrýchlenia učenia.

Feature selection - rozdelenie atribútov podľa relevantnosti
- Silno relevantné - IDEÁLNA PODMNOŽINA
- Slabo relevantné neredundantné - IDEÁLNA PODMNOŽINA
- Slabo relevantné redundantné
- Šum


---
- [[Učenie s učiteľom]]
- [[Učenie bez učiteľa]]
- [[Učenie s posilňovaním]]
---