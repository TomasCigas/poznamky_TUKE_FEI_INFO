# Vzdialenosti v grafe

## Komponent
- **komponentom** [[Grafy|grafu]] je jeho **maximálny** [[Vlastnosti grafov#Súvislosť|súvislý]] [[Špeciálne typy grafov#Podgraf|podgraf]]

## Maticové reprezentácie grafov

### Matica incidencie
- matica typu, ktorá zaznamenáva incidenciu hrán a vrcholov, kde (dohodou) každý riadok $i$ reprezentuje vrchol $v_i$ a každý stĺpec $j$ reprezentuje hranu $h_j$
- prvok $A_{i,j}$ v matici môže nadobudnúť hodnotu:
	- 1 -> pokiaľ vrchol $v_i$ inciduje s hranou $h_j$
	- 0 -> pokiaľ nie

- sčítaním všetkých prvkov v riadku $i$ dostávame [[Vlastnosti grafov#Stupeň vrchola v grafe|stupeň vrchola]] $\delta_{vi}$

### Matica susednosti
- štvorcová matica ktorá zaznamenáva susednosť jednotlivých vrcholov, kde každý riadok a stĺpec $i$ znázorňuje jeden z vrcholov
- prvok $A_{i,j}$ v matici môže nadobudnúť hodnotu:
	- 1 -> pokiaľ vrchol $v_i$ a $v_j$ sú susedné (resp. ak existuje hrana $h_{i,j}$)
	- 0 -> pokiaľ nie
- sčítaním všetkých prvkov v riadku či stĺpci $i$ dostávame [[Vlastnosti grafov#Stupeň vrchola v grafe|stupeň vrchola]] $\delta_{vi}$

### Diagonálna matica
- prvky na diagonále majú stupeň korešpondujúcich vrcholov
$$
\begin{bmatrix}
\delta_{v_1} & 0 & 0 & ...\\
0 & \delta_{v_2} & 0 & ...\\
0 & 0 & \delta_{v_3} & ...\\
... & ... & ... & \delta_{v_i}
\end{bmatrix}
$$

## Vzdialenosť vrcholov
- vzdialenosť susedných vrcholov je 1
- dokážeme zistiť manipuláciou s [[#Matica susednosti|matice susednosti]] $B$:
1. Na zistenie vzdialenosti väčších ako 1 pripočítame k $B$ jednotkovú maticu $E$ rovnakej veľkosti a dostávame $B^{(1)}$ :
$$
E = 
\begin{bmatrix}
1 & 0 & 0 & ...\\
0 & 1 & 0 & ...\\
0 & 0 & 1 & ...\\
... & ... & ... & 1
\end{bmatrix}
$$

2. následne vypočítame $B^{(k)}$:
$$
B^{(k)} = B^{(k-1)} * B^{(1)}
$$ 
- pri čom násobenie a sčítanie v matici je boolovské
3. Prvok $a_{i,j}$ matice $B^{(k)}$ nadobúda hodnoty:
	- 1 -> pokiaľ vrcholy $v_i$ a $v_j$ majú vzdialenosť **menšiu alebo rovnú** ako $k$
	- 0 -> pokiaľ vrcholy $v_i$ a $v_j$ majú vzdialenosť **väčšiu** ako $k$