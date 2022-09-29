# Lexikálna analýza
Je súčasťou [[Gramatika#Kompilátory|kompilátora]], kde sa používa na premenu lexémy na tokeny.

- **Lexémy** -> Kľúčové slová/symboly, ktoré program rozpoznáva
	- popisujú sa prostredníctvom [[Gramatika|regulárnych gramatík]], [[Gramatika#Deterministické konečno-stavové automaty|kone]][[Gramatika#Nedeterministické konečno-stavové automaty|čnými]] automatmi a regulárnymi výrazmi
- **Tokeny** -> Vnútorný kódovaný tvar lexémy
- **Vzory** -> Množina reťazcov popisujúca tokeny

## Backusova-Naurova forma
Slúži na zápis [[Gramatika#Klasifikácia|bezkontextových gramatík]].

BNF je sada odvodzovacích pravidiel zapísaných formou:
< symbol > ::= < výraz so symbolmi >,
kde symbol je neterminál a výraz so symbolmi sa skladá z terminálov aj neterminálov, ich sekvencia je oddelená **|**, prípadne sa používa zátvorková notácia.

## Rozšírená Backusova-Naurova forma
Slúži na zápis [[Gramatika#Klasifikácia|bezkontextových gramatík]].

Rozdiel od normálnej je povolenie odvádzať do prázdnych množín. Taktiež podporuje rekurziu.

- **Priorita** -> určuje ktorý operátor má prednosť *napr. x > +*
- **Asociatívnosť** -> schopnosť operátorov spájať operandy
	- **Ľavá**: E-> T {° T} *({ } -> terminálny uzáver), napr.: 1+2* 
	- **Pravá**: E -> T [° T] -> *([] ), napr $x^2$*
	- **Neasociatívnosť**: E -> T [° T] *napr. $1 \neq 2$*

