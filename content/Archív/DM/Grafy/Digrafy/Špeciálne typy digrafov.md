# Špeciálne typy digrafov

## Koreňový strom
**Koreňový strom** je orientovaný [[Špeciálne typy grafov#Strom|strom]], kde z vrcholu $v$ nazývanom **koreň** existuje [[Postupnosť vrcholov a orientovaných hrán#Dráha|dráha]] do každého ďalšieho vrchola.

Koreňový strom obsahuje len jeden [[Digrafy|prameň]] nazývaný **koreň** a všetky [[Digrafy|ústia]] sa nazývajú **listy**.

### Binárne stromy
**Binárny strom** je [[#Koreňový strom|koreňový strom]], ktorého každý vrchol môže byť [[Digrafy|začiatok]] buď 0 alebo 2 hrán
- Pri binárnych stromoch sa definuje:
	- **hĺbka stromu** -> excentricita koreňa
	- **list** ->
	- **kompletný strom** -> strom, ktorého každý list má excentricitu koreňa

## Acyklický
**Acyklický** [[Digrafy|digraf]] neobsahuje [[Postupnosť vrcholov a orientovaných hrán#Cyklus|cyklus]].
Zistenie algoritmom:
1. Hľadáme ľubovoľný [[Digrafy|prameň]]
2. Pridáme mu číslo našej iterácie
3. Vraciame sa na 1. pri čom vynecháme tento prameň
4. Všetky [[Digrafy|ústia]] iterujeme ako posledné
5. - Pokiaľ nevieme nájsť ďalší prameň, digraf je cyklický
	- Pokiaľ sme očíslovali všetky vrcholy, graf je acyklický