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
Namiesto vzdialenosti bodov od centra ([[#K-means]]) sa berie do úvahy ich hustota - teda klastruje body, ktoré sú blízko seba (body s *MinPts* počtom susedov), pri čom označuje body, ktoré sa nachádzajú v nízko-hustotných oblastiach ako [[Inteligentné systémy v informatike#Predpsracovanie dát|outlierov]].

Algoritmus:
1. Označenie typu bodov
	- *Hlavný bod* - minimálne *MinPts* bodov je vo vzdialenosti E
	- *Hraničný bod* - má menej ako *MinPts* bodov, ale nachádza sa vo vzdialenosti E
	- *Šum* - ostatné body
2. Označenie hl. bodov (resp. skupinu ních) ako klastrov
	1. Náhodne vyberieme bod a pridáme ho do klastra.
	2. Každý hlavný a hraničný bod (ešte nezaradený do klastra), ktorý sa nachádza vo vzdialenosti E od tohto bodu pridáme do klastra a opakujeme pre každý takto pridaný hlavný bod.
	3. Potom opakujeme od 1, ale len pre body, ktoré sme ešte nepridali.

Výhodou oproti k-means je, že nepredpokladá sférické klastre a taktiež nemusíme určovať počet klastrov