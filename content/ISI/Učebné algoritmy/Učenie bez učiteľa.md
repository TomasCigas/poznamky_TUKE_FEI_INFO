Algoritmus **nemá** označený data set, ako pri [[#Učenie s učiteľom|učiteľovi]]. Preto si obvykle robí závery na báze vlastného rozhodnutia a typu:
- **Klastrovanie**
	- algoritmus rozdeľuje vzorky podľa podobnosti, teda vytvára *klastre*.
![[clustrovanie.excalidraw]]


# K-means
Je to založené na prototypoch C:
- centroid - priemer podobných hodnôt
- medoid - najčastejšie sa vyskytujúce

Algoritmus:
1. Náhodne sa vyberie C
2. Pridelia sa vzorky k C
3. C sa presunie do stredu vzoriek
4. Opakujeme pre všetky vzorky / do istej podmienky

Nevýhodou sú nekonvenčne rozdelené dáta (teda ak nemajú sférový tvar v priestore). Podobnosť bodov je vypočítaná ako obrátená hodnota ich vzdialenosti.

Počet klastrov počítame *lakťovou metódou*, teda hľadáme v grafe *Chyba*/*Počet klastrov* "lakeť" (významný zlom pri spojení bodov)
![[laket.excalidraw]]

# DBSCAN
Rozšírenie [[#K-means|k-means]] o koncept hustoty, teda namiesto vzdialenosti bodov berie do úvahy ich hustotu - teda počet bodov vo vzájomnej vzdialenosti s polomerom E

Algoritmus:
1. Označenie typu bodov
	- *Hlavný bod* - minimálne *MinPts* bodov je vo vzdialenosti E
	- *Hraničný bod* - má menej ako *MinPts* bodov, ale nachádza sa vo vzdialenosti E
	- *Šum* - ostatné body
2. Označenie hl. bodov (resp. skupinu ních) ako klastrov

Výhodou oproti k-means je, že nepredpokladá sférické klastre