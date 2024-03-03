***********
Definícia AS:
- definícia **konfigurácie** AS
- definícia **inštrukcií** AS
	- syntax inštrukcií
	- [[Operačná sémantika|operačná sémantika]] inštrukcií

# Konfigurácia
Konfigurácia vyzerá následovne:
$$
\langle c,st,s \rangle
$$
kde: 
- $c$ je kód, teda postupnosť inštrukcií
- $st$ je zásobník hodnôt
- $s$ je stav, alebo dynamická pamäť programu

*Zásobník* je sémantická oblasť, ktorá reprezentuje *Stack* štruktúru a slúži na rýchlu prácu s hodnotami.

# Operačná sémantika inštrukcií

Je to v podstate normálna [[Operačná sémantika|operačná sémantika]] s tvarom:
$$
\langle c,st,s \rangle =>> \langle c',st',s' \rangle
$$
Konečná konfigurácia má tvar:
$$
\langle \epsilon,st,s \rangle
$$



---
