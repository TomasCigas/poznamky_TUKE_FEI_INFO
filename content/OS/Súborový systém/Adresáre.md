# Adresár
Adresár je špeciálny [[Súborový systém|súbor]] (priečinok), ktorý na disku logicky zoskupuje iné súbory.

Podstata adresárov je v mapovaní [[Súborový systém#Atribúty súboru|mena]] súboru.

Má podobné **operácie** ako súbor:
- Vyhľadávanie súboru
- Vytvorenie súboru
- Vymazanie súboru
- Vypísanie obsahu adresára
- Premenovani súboru
- Prechádzanie súborového systému

## Štruktúra adresárov
### Jednoúrovňové
Jedná sa o zapísanie jednotlivých [[Súborový systém#Atribúty súboru|atribútov]] a smerníka na súbory za sebou:
![[single_lvl_dir.excalidraw]]

Výhody:
- jednoduchá implementácia
- zaberá málo miesta

Nevýhody:
- neposkytuje výhody ostatných štruktúr 

### Dvojúrovňové
Implementuje už aj schopnosť prideľovať jednotlivé súbory viac používateľom jedného počítača.
![[two_lvl_dir.excalidraw]]

Výhody:
- umožňuje odelenie súborových systémov podľa používateľa

Nevýhody:
- zaberá viac miesta

### Viacúrovňové
#### Stromová štruktúra
![[tree.png]]
#### Acyklický graf
![[acycle.png]]

Ušetrenie miesta na disku.
#### Všeobecný graf
![[general.png]]

## Adresárové služby
