# Reprezentácia grafov
**Grafy** sa bežne využívajú na reprezentáciu [[Množiny a množinové relácie|relácií]] medzi objektmi.

## Systematické prechádzanie grafom
[[#Do hĺbky|DFS]] a [[#Do šírky|BFS]] sa používajú ako rámce pre návrh rôznych efektívnych algoritmov.
Musíme zvažovať aj či je graf súvislý alebo nie.

### Do hĺbky
(depth-first search)
- **navštevovanie susediacich vrcholov** pokiaľ to je možné
- pokiaľ nie, **vrátime sa späť** a volíme inú cestu (vhodné na používanie ([[Varianty zoznamov#Varianty zoznamov#Zásobník|zásobníka]]))
- opakujeme dokedy neprejdeme **všetky vrcholy**
- najprv sa prehľadáva do **hĺbky**, potom do **[[#Do šírky|šírky]]**

**Zložitosť**:
- $T(n) = O(m)$, kde $m = card(E)$, $n = card(V)$; $n\leq m$
- počet volaní procedúry je daný $n$ (max. pre každý vrchol)
- čas strávený v r.2 a 3 je úmerný súčtu dĺžok zoznamov susednosti ($O(m)$)

### Do šírky
(breadth-first search)
- najprv sú navštívení susedia, potom susedia susedov a tak ďalej
- využívame [[Varianty zoznamov#Front|front]]

**Postup**:
- začiatočný vrchol označíme ako navštívený, vložíme do frontu
- vyberieme prvý vrchol z frontu, jeho nenavštívených susedov označíme a pridáme do frontu
- pokračujeme dokým nebude front prázdny

**Zložitosť**:
- každý vrchol v Q bude navštívený raz
- každá hrana bude preskúmená 2x
- teda $T(n) = O(max(m,n))$