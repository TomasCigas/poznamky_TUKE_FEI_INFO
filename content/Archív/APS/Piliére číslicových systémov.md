# Piliére číslicových systémov

## Abstrakcia
Špecifikuje kompozíciu systému.

Abstrakcia skrýva detaily, ktoré nie sú podstatné z hľadiska hardvéru na príslušnej úrovni.

Má viacero úrovní: na **najnižšej úrovni** sa nachádza opis komponentov z hľadiska ich fyzikálnych vlastností; na **najvyššej úrovni** sa nachádza aplikačný softvér.

## Disciplína 
Jedná sa o úmyselné obmedzenie návhrhových rozhodutí, aby sme mohli pracovať na vyššej úrovni [[#Abstrakcia|abstrakcie]].

Napr. obmedzenie používania napätia nám umožňuje prehľadnejšie a efektívnejšie navrhovať systémy.

## Trojica HMJ
### Hierarchia
- rozdelenie systému do [[#Modularita|modulov]] a následne podmodulov
- zlepšuje pochopiteľnosť jednotlivých častí systému

### Modularita
- moduly majú dobre definované funkcie a rozhrania
- moduly sa jednoducho spájajú bez nepredvídaných vedľajších účinkov

### Jednotnosť
- jednotnosť medzi modulmi -> spoločné moduly sa opakovane používajú
- znižuje počet odlišných modulov => menej modulov na navrhovanie