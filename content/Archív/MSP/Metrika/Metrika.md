*********************************
*Metrika* je numerický klasifikátor, pomocou ktorého dokážeme porovnávať služby, či javy.
Metrika musí nejakým spôsobom nadväzovať na reálny svet.

Metrika sa používa na vytváranie a vyhodnocovanie teoretických modelov. Všeobecne nám slúži na zefektívnenie *produktu* a *procesu* jeho výroby (vďaka porovnávaniu s ostatnými projektmi).

*Meranie* je pozorné pozorovanie, ktoré slúži na identifikovanie nových fenoménov. 
**Meranie je mapovanie reálneho sveto do formálneho**, kde nad ním môžeme neflexibílnym (obmedzeným) spôsobom pozorovať javy. Zväčšením škály mapovania sa zvyšuje presnosť pozorovania, ale taktiež aj komplexita jeho spracovania.

# Produktové metriky
Hovoria o výsledku projektu.

## Extérne
Sú od používateľov.
- *Nespoľahlivosť* - Defekty a nepresnosti produktu (koľko chýb ešte v ňom ostáva)
- *Náklady* - aké zdroje produkt potrebuje + cena
- *Použiteľnosť* - ako jednoducho sa produkt používa a učí jeho používanie
- *Funkcionalita* - čo všetko produkt ponúka
- *Výkon* - využitia zdrojov

## Intérne 
Od vývojárov.
- *Veľkosť*
- *Komplexita* - ako ťažko sa projekt upravuje (z pohľadu vývojára)
- *Štýl* - pochopiteľnosť produktu pre vývojárov + dokumentácia

# Procesné metriky
## Extérne 
Ako sa produkt (systém) správa v reálnom svete
## Intérne 
Ako boli zvládnuté jednotlivé časti vývoja


# Softvérové metriky

## Lines Of Code (LOC)
Vychádza z Assembleru, kde produktivita vychádala z počtu riadkov. Používa sa aj statická analýza, ktorá vyhodnocuje všetky nedosiahnuteľné stavy / príkazy.

## Cyklomatická komplexita
Vyhodnocuje schopnosť správy kódu. Využíva teóriu grafov: z kódu / programu vytvorí graf $V(G) = e - n+2p$, kde $e=$ hrany, $n=$ uzly, $p=$ spojené komponenty.

*Hodnoty CC pre jeden modul*: 

Počet|typ|risk
---|---|---
1-4|jednoduchý|nízky
5-10|jednoduchý|nízky
11-20|komplexný|stredný
21-50|veľmi komplexný|vysoký
50+|extrémne problematický|veľmi vysoký

Ideálna CC 1 modulu by mala byť $\leq$ 10.

## Fan-in & Fan-out
*Fan-in* - počet vstupov do modulu.
*Fan-out* - počet výstupov z modulu.

Podobne ako pri [[#Cyklomatická komplexita|CC]] veľké množstvo F-in alebo F-out, môže značiť zlý dizajn modulu.

## Funkčné body (FP)
Značí/meria funkcie a funkcionality produktu -> hodnotený z pohľadu používateľa.
Výhodou funkčných bodov je tvorba benchmarku produktov a pre tímy. Sme schopných ich použiť v celom životnom kolobehu projektu.

Postup použitia FP:
- hrubý vstup v tvare UFP
- upravíme UFP na VAF a AFP
	- VAF - koordinačná konštanta : 0.65
	- VAF -nadobúda od 0.65 po 1.35
- zistíme LOC v našom prípade
- zistíme komplexitu [[COCOMO|COCOMO]]
- pracujeme s tým na výpočet trvania a úsilia

*Experimentálne pravidlá pre FP*:
- $1 FP$ ~ 100 LOC a 50 LOC pre OOP
- $FP^{1.15}=$ počet strán dokumentácie
- $FP_{(m+1)}~FP_m*1.01=$ "používateľov apetít"
- $FP^{1.12}=$ počet testov
- Review zisťuje cca $30\%$ testov.
- $FP^{0.4}$ ~ čas vývoja
- $FP/150$ ~ počet pracovníkov na vývoji
- $FP/500$ ~ počet pracovníkov na správe


## Znovapoužiteľnosť
*Znovapoužiteľnosť* kódu nám môže rozhadzovať niektoré metriky, napr. [[#Lines Of Code (LOC)|LOC]], nakoľko zvyšuje komplexitu v začiatočných fázach, ale môže ju znížiť v iných.

*******
- [[COCOMO]]
*******