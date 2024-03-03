***********
**Syntax programovacích jazykov** určuje tvar a štruktúru programov písaných v tomto jazyku.

Existuje mnoho druhov syntaxe, avšak z pohľadu formálnej definície jazyka sa budeme pozerať na:

# Abstraktná syntax
Zaoberá sa len **štruktúrou programu**.

**Definícia** pozostáva z:
- syntaktické oblasti
- strom abstraktnej syntaxe

**Strom abstraktnej syntaxe**:
- v uzloch sú prvky syntaktickej oblasti - [[Konštrukcie]]
- v listoch sú atomické entity - samotné hodnoty
- hrany sú argumenty konštrukcie

Produkčné pravidlá sú v tvare:
$$
prvok\_syntatickej\_oblasti ::= tvar_1|tvar_2|...
$$

# Konkrétna syntax
Zaoberá sa zápisom programu a slúži na kontrolu programu (či bol zapísaný správne).

- určuje, či veta patrí do jazyka
- poskytuje **syntaktický strom** pre $\forall$ akceptovaný program
- špecifikované **[[Gramatika|formálnou gramatikou]]** a produkčnými pravidlami


---