# Inteligentné systémy v informatike
V tomto predmete sa zameriavame na **Machine Learning** (ML), alebo strojové učenie.

## Kocnepty ML
Strojové učenie má za úlohu vytvoriť **algoritmus**, ktorý dokáže robiť rozhodnutia na základe jeho vstupu. Rozhodnutie závisí od typu učenia:

### Učenie s učiteľom
Náš algoritmus sa uči prostredníctvom **označeného data setu**.

Rozdelenie:
- **Klasifikácia**
	- hodnota, ktorú predikujeme má konečný počet značiek (variácií)
	- teda rozdeľujeme vstupy podľa značiek a algoritmus 
- **Regresná analýza**
	- počet značiek nie je konečný
	- obvykle ide o reálne číslo (teda počet je nekonečný)

### Učenie bez učiteľa
Algoritmus **nemá** označený data set, ako pri [[#Učenie s učiteľom|učiteľovi]]. Preto si obvykle robí závery na báze vlastného rozhodnutia a typu:
- **Klastrovanie**
	- algoritmus rozdeľuje vzorky podľa podobnosti, teda vytvára *klastre*.
![[clustrovanie.excalidraw]]
- **Redukcia [[Terminológia a označenia v ISI|dimenzionality]]**
	- jedná sa o redukciu počtu vzoriek, za účelom zlepšenia, alebo zrýchlenia učenia
	- ==Spýtať sa na korektnosť==

### Učenie s posilňovaním
Za každú vykonanú akciu dostane algoritmus spätnú väzbu vo forme **odmeny**, podľa ktorej robí zmeny.

---
- [[Terminológia a označenia v ISI]]
- [[Systém strojového učenia]]
---