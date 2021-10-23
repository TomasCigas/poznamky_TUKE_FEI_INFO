# Množiny a množinové relácie

**Množina** - súbor nejakých navzájom odlišných objektov, ktorého podľa nejakého kritéria tvoria jeden celok.

Pokiaľ prvok patrí množine: $a\ \epsilon\ A$
Prázdna množina: $A = \emptyset$

## Potenčná množina
**Potenčná množina** množiny $A$ je množina $P(A)$, ktorej prvkami sú všetky podmnožiny množiny $A$

## Relácie
**Relácia** je ľubovoľná podmnožina karteziánskeho súčinu.

## Karteziánsky súčin
**Karteziánsky súčin** je množina všetkých usporiadaných n-tíc, kde každý prvok n-tice patrí jednej z množín.

## Binárna relácia
**Binárna relácia** z množiny A do množiny B je ľubovoľná podmnožina karteziánskeho súčinu $A\times B$. Ak $A=B$, hovoríme o binárnej relácii na množine A, čo je ľubovoľná podmnožina $R\subset A^2$

## Zobrazenie
**Zobrazenie** z množiny A do množiny B je binárna relácia
s vlastnosťami:
- Ku $\forall a\ \epsilon A;$ existuje $b\ \epsilon B$ tak, že $(a,b\ \epsilon f)$
- Ak $(a,b)\epsilon f\ \wedge\ (a,c)\epsilon f$ tak $b=c$

_input file_

### Druhy zobrazení
1. **Surjektívne**: Ak ku každému $b\ \epsilon\ B$ existuje aspoň jedno $a\epsilon\ A$ tak, že $b=f(a)$
2. **Injektívne**: Ak z $a_1\neq a_2$, $a_1,a_2\ \epsilon\ A$ vyplíva $f(a_1) \neq\ f(a_2)$
3. **Bijektívne**: ak je injektívne a surjektívne

## Vlastnosti binárnych množín
1. **Reflexívnosť**: Ak $\forall a\ \epsilon\ A$ platí $aRa$
2. **Symetrickosť**: Ak $\forall a,b\ \epsilon\ A$ platí, že ak $aRb$, tak aj $bRa$
3. **Antisymetrickosť**: Ak $\forall a,b\ \epsilon\ A$ platí, že ak $aRb\ \wedge bRa$, tak $a=b$
4. **Tranzitívnosť**: Ak $\forall a,b,c\ \epsilon\ A$ platí, že ak $aRb\ \wedge bRc$, tak $aRc$

## Ekvivalencia
Hovoríme, že $R$ na množine $A$ je **ekvivalencia** na množine A, ak je *reflexívna*, *symetrická* a tranzitívna.