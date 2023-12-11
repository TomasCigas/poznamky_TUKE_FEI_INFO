***********
Učebné algoritmy s rôznymi požiadavkami a postupmi.

Strojové učenie má za úlohu vytvoriť **program**, ktorý dokáže robiť rozhodnutia na základe jeho vstupu. Rozhodnutie závisí od typu učenia.

# Metódy evaluácie modelov a ladenia hyperparametrov
Ladením **[[Terminológia a označenia v ISI|hyperparametrov]]** dosahujeme lepšie výsledky z našich modelov.

Obvykle ladíme:
- Iteračne
- Random
- Zmiešane (aj iteračne aj random)

*Zlé nastavenie hyperparametrov (+ iné podmienky) môžu spôsobovať*:
- **Overfitting** (pretrénovanie) - vypracovanie analýzy, teda model, ktorý príliš blízko alebo presne zodpovedá konkrétnemu súboru hodnôt nemusí byť vhodne vypracovaný pre dodatočné informácie, ktoré dostane pri predikcii, a preto nespoľahlivo predpovedá budúce pozorovania
	- inak povedané sa model začne učiť aj na šume a nie len na relevantných hodnotách
- **Underfitting** (podtrénovanie) - model nedokáže adekvátne zachytiť základnú štruktúru údajov buď tým, že sme nepoužili správny predikčný model (prípadne nedostatočne naladili) alebo nedostatkom dát, prípadne atribútov
	- jednoducho model je nepresný, pretože sa nemohol (prípadne nedokázal) naučiť dostatok informácií.

Pri ladení môže dôjsť ku pretrénovaniu modelu, tomuto predchádzame *validáciou modelu*:
- **Hold-Out** - rozdelíme dáta na 3 sady (trénovacie, validačné a testovacie), kde túnujeme model len na dvoch z nich a potom testujeme s tretím
- **Cross-validation** - dáta rozdelíme na $k$ častí a trénujem model $k$-krát. (tzv. $k$-fold)
	- vystupuje tu k-fold parameter, ktorý hovorí na koľko častí rozdelíme dáta
	- *stratified k-fold* - dáta sa rozdeľujú na rovnomerné časti
	- *nonstratified k-fold* - dáta sa rozdeľujú v náhodnom pomere
- **Diagnostika pomocou kriviek učenia a validácie** - krivky nám ukazujú, či sme model pod/pretrénovali
	- ![[krivky_diagnost.excalidraw]]
	- kde plnou čiarou sú reálne výsledky testovania a čiarkovanou zdánlivé krivky validácie

**Riešenie pod/pretrénovania**:
- *Podtrénovanie* - pridať atribúty, spresniť hyperparametre
- *Pretrénovanie* - pridať vzorky, zjemniť hyperparametre, odobrať atribúty

**Metriky pre evaluáciu výkonnosti**:
*Matica zámien* nám určuje aký druh chyby náš model zrobil
![[matica_zamien.excalidraw]]

True Positive Rate (sensitivity): $TPR=\frac{TP}{P}=\frac{TP}{TP+FN}=1-FNR\rightarrow$ False Negative Rate
True Negative Rate (specicifity): $TNR=\frac{TN}{N}=\frac{TN}{TN+FP}=1-FPR\rightarrow$ False Positive Rate
Positive Predictive Value (precision): $PPV=\frac{TP}{TP+FP}=1-FDR\rightarrow$ False Discovery Rate
Accuracy: $ACC=\frac{TP+TN}{P+N}$

# Redukcia dimenzionality
**Redukcia [[Terminológia a označenia v ISI|dimenzionality]]** -  jedná sa o redukciu počtu vzoriek a/alebo atribútov, za účelom zlepšenia, alebo zrýchlenia učenia (bez straty presnosti).

**Feature selection** - rozdelenie atribútov podľa relevantnosti
- Silno relevantné - IDEÁLNA PODMNOŽINA
- Slabo relevantné neredundantné - IDEÁLNA PODMNOŽINA
- Slabo relevantné redundantné
- Šum

# Systém strojového učenia
![[machine_learning_system.excalidraw]]

---
- [[Učenie s učiteľom]]
- [[Učenie bez učiteľa]]
- [[Učenie s posilňovaním]]
---