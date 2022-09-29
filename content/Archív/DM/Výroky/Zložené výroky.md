# Zložené výroky
- [[Výroky|zložené výroky]] sa zvyknú vyjadrovať **pravdivostnou tabuľkou**, v ktorej sa vypíše každá možná variácia zloženého výroku a následne sa vyhodnotí, akú hodnotu nadobúda celý zložený prvok
	- pokiaľ má každá variácia pravdivostných hodnôt zloženého prvku hodnotu _pravda_ (1), hovoríme takémuto výroku **tautológia**, napoak pokiaľ majú _nepravdu_ (0), hovoríme mu **kontradikcia**

- pokiaľ majú dva výroky rovnakú pravdivostnú hodnotu, aj keď nemajú rovnaký zápis, hovoríme, že tieto výroky sú **kongruentné** (ozn. $A|=B$ )

- jednotlivé výroky (v tomto prípade len $A$ a $B$) sá vo výrokovej logike spájajú predurčenými spôsobmi -> základnými **[[#Logické spojky|logickými spojkami]]**

- pri vyhodnocovaní pravdivostnej hodnoty jednotlivých prvkov používame tzv. **vytváraciu postupnosť** -> každý člen postupnosti je definovaný cez členov s nižším indexom (s nižším počtom logických spojok)
	- napr.: $A=(p\vee \neg q) \Rightarrow r$, postupnosť je:
		- $p$, $q$, $r$, $\neg q$,$p\vee \neg q$, $(p\vee \neg q) \Rightarrow r$


# Logické spojky
## Konjukcia
- ozn.: $A \wedge B$
- pravda, pokiaľ sú obe výroky pravdivé
- pravdivostná tabuľka:

A|B|$A\wedge B$
------------ | ------------| ------------
0|0|0
0|1|0
1|0|0
1|1|1

- pozn.: konjukcia je komutatívna

## Disjunkcia
- ozn.: $A \vee B$
- pravda, pokiaľ aspoň jeden výrok je pravdivý
- pravdivostná tabuľka:

A|B|$A\vee B$
------------ | ------------| ------------
0|0|0
0|1|1
1|0|1
1|1|1


## Implikácia
- ozn.: $A \Rightarrow B$
- pravda, dokým nepravda neimplikuje pravdu
- pravdivostná tabuľka:

A|B|$A\Rightarrow B$
------------ | ------------| ------------
0|0|1
0|1|0
1|0|1
1|1|1

## Ekvivalencia
- ozn.: $A \Leftrightarrow B$
- pravda, keď sú oba výroky rovnaké
- pravdivostná tabuľka:

A|B|$A\Leftrightarrow B$
------------ | ------------| ------------
0|0|1
0|1|0
1|0|0
1|1|1

- pozn.: ekvivalencia je komutatívna

## Negácia
- táto aj keď nespája dva výroky, mení pravdivostnú hodnotu výroku
- ozn. $\neg A$

A|$\neg A$
--|--
0|1
1|0
