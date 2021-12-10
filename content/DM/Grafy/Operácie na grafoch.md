


# Operácie na grafoch
Nech $G_1=(V_1,H_1)$ a $G_2=(V_2,H_2)$ sú [[Grafy|grafy]].
## Zjednotenie a prienik
Potom:
- **Zjednotenie** grafov $G_1$ a $G_2$ nazývame graf $G = (V_1 \cup V_2,H_1 \cup H_2)$.
- **Prienik** grafov $G_1$ a $G_2$ nazývame graf $G = (V_1 \cap V_2,H_1 \cap H_2)$.

## Farbenie
cwayons hehe

## Vrcholov
Princípy farbenia:
1. Farbíme vrcholy
2. Susedné vrcholy majú rôzne farby
3. Chceme použiť čo najmenej farieb

- počet farieb, ktoré použijeme sa nazýva **chromatické číslo**
- graf môže mať minimálne chromatické číslo = 
	- 1 pokiaľ sa v ňom nenachádzajú hrany
	- 2 pokial je v grafe aspoň 1 hrana a graf je [[Špeciálne typy grafov#Biparitný graf|párny]]
	- 3 pokiaľ je v grafe [[Postupnosť vrcholov a hrán#Kružnica|kružnica]] s nepárnym počtom vrcholov
- maximálne chromatické číslo je = maximálnemu stupňu + 1

Postup farbenia vrcholov:
1. Zistíme minimálne a maximálne chromatické číslo
2. Farbíme minimálne, dokým nenarazíme na spor
Typy:
- prioritizujeme jednoznačné farby pri minimálnom chromatickom čísle
- pri symetrickom grafe môžeme farbiť najprv vonkajšiu kružnicu

## Hrán
Princíp farbenia:
1. Farbíme hrany
2. Susedné hrany majú rôzne farby
3. Chceme použiť čo najmenej farieb

- počet farieb, ktoré použijeme sa nazýva **chromatický index**
- graf môže nadobúdať chromatický index:
	- [[Vlastnosti grafov#Stupeň vrchola v grafe|maximálneho stupňa]] -> graf 1. triedy
	- maximálneho stupňa + 1 -> graf 2. triedy

Postup farbenia hrán je podobný ako pri [[#Vrcholov|vrcholoch]].