******************************
V tomto predmete sa zameriavame na **[[Učebné algoritmy|Machine Learning (strojové učenie)]]** a **[[Vyhľadávacie problémy|umelú inteligenciu]]**.

# Predpsracovanie dát
Jedná sa o prípravu dát na učenie algoritmom.
**OUTLIER** - vzorka, ktorá sa nachádza mimo trendu, snažíme sa tieto vzorky buď zahodiť, alebo naopak práve nájsť (rôzne dôvody)

**Spracovanie chýbajúcich dát**:
- Vymazanie vzorky 
- Dosadenie vzorky (priemer, medián a i.)
- Zaobstarávame sa kategorickými vzorkami (napr. stringy):
	- ordinálne (dokážeme ich medzi sebou porovnať)
	- nominálne (sú osobitné/neporovnateľné)
	- Prístupy LabelEncoding, OridnalEncoding a One Hot Encoding

**Škálovanie**:
Dáta sa snažíme **normalizovať** (hodnota od 0 po 1) **štandardizovať** (hodnota okolo 0) aby sme odstránili preferenciu veľkých/malých hodnôt v jednotlivých atribútoch.

Predspracovanie dát musí prebiehať aj na naších neznámych/predikčných dátach, avšak nastavenie parametrov (napr. labels pri LabelEncoder) musí prebiehať len na trénovacích, keďže môže dochádzať k bleedingu informácie.

---
- [[Terminológia a označenia v ISI]]
- [[Učebné algoritmy]]
- [[Vyhľadávacie problémy]]
---