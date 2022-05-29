# Formálne jazyky
## Základné termíny
**Programovací jazyk** -> Prostriedok, v ktorom programátor rieši algoritmické problémy

**Formálny jazyky a gramatiky** -> teoretické prostriedky používané na tvorenie programovacích jazykov, prekladačov a kompilátorov

**Prekladač** -> Program, ktorý transformuje problém vyjadrený vo vyššom programovacom jazyku (obvykle) od jazyka strojových inštrukcií

**Jazyk strojových inštrukcií** -> Jazyk, v ktorom je problém pripravený na vykonanie v počítači

### Abeceda

**Abeceda** je konečná neprázdna množina prvkov, ktoré sa nazývajú **symboly**. Zvyčajne obsahujú písmená a/alebo čísla.
- Pre abecedu $A$ je:
	-  $A^*$ -> množina všetkých reťazcov nad abecedou ( **Tranzitivný uzáver** )
	-  $A^+$ -> množina všetkých neprázdnych reťazcov ( **Kladný uzáver** )

**Reťazec** je ľubovoľná postupnosť symbolov z abecedy.
- *prázdny reťazec* -> s nulovou dĺžkou ($\epsilon$)
- *obrátený reťazec*
- *zreťazenie reťazcov*
- pre tri zreťazené reťazce xyz
	- x -> *predpona*
	- y -> *podreťazec*
	- z -> *prípona*

**Jazyk** (formálny) je ľubovoľná podmnožina $L$ množiny $A^*$	
- $L = \emptyset$ -> prázdny jazyk
- $|L| = n$ -> konečný jazyk

---
- [[Gramatika]]
- [[Analýza]]
---