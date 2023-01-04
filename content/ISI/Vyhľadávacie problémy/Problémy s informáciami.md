***********
Algoritmy používajú evaluačnú funkciu $f(n)$, ktorá nám hovorí o riešení momentálneho stavu, resp. ako ďaleko sme v riešení nášho stavu / ako blízko sme pri riešení.

# UCS
$f(n) = c(n)$
- kde $c(n)$ je kumulatívna hodnota akcií nášho algoritmu

UCS algoritmus hľadá cestu v strome, ktorá je "najlacnejšia", teda má najmenšiu kumulatívnu hodnotu.

UCS nájde optimálne riešenie

**Časová zložitosť** - $O(b^{c^* / \epsilon})$, kde
- $\epsilon$ - minimálna váha hrany
- $c^*$ - kumulatívna váha k cieľu
**Pamäťová zložitosť** - $O(b^{c^* / \epsilon})$

# Greedy
$f(n) = h(n)$
Pridávame heuristickú informáciu $h(n)$, ktorá nám hovorí o tom, ako ďaleko sa nachádzame od cieľového stavu.

Teda *greedy* algoritmus nám expanduje stav, ktorý sa nachádza čo najbližšie k cieľovému stavu.
Sám o sebe predchádza cyklovým problémom.

Je najrýchlejší, ale nemusí nájsť optimálne riešenie.

Pokiaľ zvolíme zlú heuristiku, môže sa zmeniť na veľmi zlý DFS.

Heuristika musí byť [[#Heuristiky|prípustná]].

# A*
$f(n) = c'(n) + h(n)$, kde
$c'(n)$ je kumulatívna hodnota do momentálneho expandovaného stavu.

Je pomalší ako [[#Greedy|greedy]], ale nachádza optimálne riešenie (rýchlejšie ako [[#UCS]]).
Podobne ako pri greedy zlé zvolenie heuristiky môže spôsobiť neoptimálnosť a dlhšie vyhľadávanie + musíme dávať pozor aj na kumulatívne ceny.

Heuristika musí byť [[#Heuristiky|prípustná]].

# Heuristiky
*Návrh nových huristík*:
- heuristiku berieme z nášho stavového priestoru, snažíme sa teda zrelaxovať problém na jednoduchší a ľahko počítateľný
	- Zrelaxovaný problém supergraf $\forall$ možných stavových grafov
	- Zrelaxovaný problém by sa mal čo najviac podobať reálnej situácii na zníženie počtu expandovaných stavov.

**Dominantnosť heuristík** - ak heuristika aproximuje reálne váhy, vo všeobecnosti expanduje menší poćet uzlov, ale výpočet je náročnejší

**Prípustnosť heuristík** - heuristika musí spĺňať $h(n) \leq c(n)$

**Konzistencia (monotónnosť) heuristík** - heuristika musí spĺňať trojuholníkovú nerovnosť, teda $f(n) = g(n) + h(n)$ je *neklesajúca*

Pri vyhľadávaní v strome musí byť heuristika prípustná, pri vyhľadávaní v grafe musí byť heuristika konzistentná.