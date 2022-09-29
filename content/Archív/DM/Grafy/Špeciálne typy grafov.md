# Špeciálne typy grafov

## Pravidelný graf
- [[Grafy|graf]], ktorého všetky vrcholi majú rovnaký [[Vlastnosti grafov#Stupeň vrchola v grafe|stupeň]].
- **k-regulárny** graf má všetky vrcholy $k$ stupňa:
	- 3-regulárny graf sa nazýva aj **kubický**

## Biparitný graf
- [[Grafy|graf]], kde množinu vrcholov $V$ je možné rozdeliť na dve skupiny, kde ani vrcholi nie sú navzájom susedné
- obsahuje len párne cykly 

## Kompletný graf
$K_n - (V,{V\choose 2}),|V|=n$ -> kompletný [[Grafy|graf]] na n vrcholoch
- každý vrchol je spojený s každým iným vrcholom grafu
- počet [[Vlastnosti grafov#Kostra|kostier]] $x$ kompletného $K_n$ grafu sa vypočíta:
$$
x = n^{n-2}
$$
- Cayleyov vzorec (kostry môžu byť izomorfné)

### Kompletný biparitný graf
- $K_{m,n}$ je [[#Biparitný graf|biparitný graf]] s vrcholmi rozdelených do $V_1$ a $V_2$, kde každý vrchol z $V_1$ je susedný s každým vrcholom $V_2$

## Prázdny graf
$G=(\emptyset , \emptyset)$

## Podgraf
Def.: Nech $G=(V,H)$ je [[Grafy|graf]]. 
Ak $V_1 \subset V$ a $H_1 \subset H$, tak graf $G_1 = (V_1,H_1)$ je podgrafom grafu $G$. 
- ozn. $G_1 \subset G$ . 
- Každý graf je podgraf seba samého.

## Strom
- neprázdny súvislý [[Grafy|graf]], ktorý neobsahuje [[Postupnosť vrcholov a hrán#Kružnica|kružnice]]
- Typy stromov:
![[graf5.png]]
- Pre stromy platí:
	- $|H| = |V| - 1$
	- medzi každou dvojicou vrcholov existuje práve jedna cesta