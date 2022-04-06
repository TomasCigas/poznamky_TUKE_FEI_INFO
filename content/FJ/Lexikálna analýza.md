# Lexikálna analýza

Slúži na kontrolu chýb v kóde. je súčasťou kompilátora, kde sa používa na kontrolu chýb:
#add_link 
- Syntaktické chyby
- Lexikálne chyby
- Sémantické chyby
- Logické chyby


## Lexémy
Kľúčové slová/symboly, ktoré dokáže program spoznať.

## Rozšírená Backusova-Naurova forma
Slúžina zápis bezkontextových gramatík.
#add_link


Rozdiel od normálnej je povolenie odvádzať do prázdnych množín. Taktiež podporuje rekurziu.

- **Priorita** -> určuje ktorý operátor má prednosť *napr. x > +*
- **Asociatívnosť** -> schopnosť operátorov spájať operandy
	- **Ľavá**: E-> T {° T} *({ } -> terminálny uzáver), napr.: 1+2* 
	- **Pravá**: E -> T [° T] -> *([] ), napr $x^2$*
	- **Neasociatívnosť**: E -> T [° T] *napr. $1 \neq 2$*

