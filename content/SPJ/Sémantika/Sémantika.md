***********
**Sémantika** sa zaoberá významom programov napísaných v programovacom jazyku.

Programovacie jazyky sa [[content/SPJ/Syntax/Syntax|skladajú]] z rôznych *konštrukcií* (deklarácie, výrazy...).

# Formálna sémantika
Poskytuje abstraktné jednotky, ktoré reprezentujú **podstatné črty** všetkých možných programov
Ignoruje detaily, ktoré nie sú z hľadiska významu programu podstatné.

**Podstatné črty**:
- Vzťah medzi vstupom a výstupom
- Terminovanie alebo neterminovanie procesu

# Výrazy

## Aritmetické výrazy
Aritmetické výrazy sú matematické výpočty, či relácie nad nejakou množinou čísel. V tomto prípade budeme počítať len s celými číslami ($Z$).

Sémantická funkcia pre aritmetické výrazy je:
$$
\textbf{E} : Expr \rightarrow State \rightarrow Z
$$
Funkcia $E$ má vstupné argumenty ($Expr$ a $State$) výstupom funkcie je v tomto prípade celé číslo ($Z$).
[[Funkcie|Curryovský zápis]] funkcie.

Aplikácia tejto funkcie je nasledovná:
1. Dosadíme prvý argument za aritmetický výraz (napr. $x+y-5$), teda:
$$
\textbf{E}\ [[x+y-5]]:State \rightarrow Z
$$
2. Aplikujeme teraz druhý parameter, teda doplníme stav s
$$
\textbf{E}\ [[x+y-5]]s = n \in Z
$$

## Boolovské výrazy
Význam boolovských výrazov môže nadobúdať len dve hodnoty:
$$
B = \{tt,ff\}
$$
pričom:
- $tt$ zaznačuje pravdivú hodnotu
- $ff$ zaznačuje nepravdivú hodnotu

Sémantická funkcia je:
$$
\textbf{B} : Bexp \rightarrow State \rightarrow B
$$
Riešenie je obdobné ako pri [[#Aritmetické výrazy|aritmetických výrazoch]].

## Stav 
Stav je abstrakciou pamäte, obvykle zapisovaný ako $s$.

Reprezentáciou stavu v písomnej forme je buď výpis všetkých premenných a ich hodnôt:
$$
s = [x\mapsto e]
$$
(kde $x$ je premenná a $e$ je jeho hodnota), alebo ako zmenu niektorej z premenných stavu:
$$
s' = s[x\mapsto e]
$$
kde $s'$ je nový stav, ktorý mení premennú $x$ na $e$.

---
- [[Konštrukcie]]
- [[Typy sémantiky]]
---