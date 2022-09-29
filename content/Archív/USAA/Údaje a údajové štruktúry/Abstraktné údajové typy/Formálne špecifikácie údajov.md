# Formálne špecifikácie údajov
Každé ADT sú *algebrou*, ktoré sa skladá z:
- základných stavebných prvkokv (*sorts*)
- konečná množina operácií (*opns*)
- konečná množina vlastností (*eqns*)

## Prirodzené číslo
**OPNS**:
- 0: -> nat
- SUCC: nat -> nat (successor => ďalšie číslo)
- ADD: nat nat -> nat
- MUL: nat nat -> nat
 

**EQNS** -> vyjadrenie vlastností (axiómy)

## Reťazec
- predpokladaná existencia ADT *alph* (abceda -> reprezentácia písmen)

**OPNS**:
- Empty : -> string
- LAdd (left add): alph string -> string
- RAdd (right add): string alph -> string
- Cat: string string -> string
- Make (pretypovanie?): alph -> string

**EQNS**:
- vychádza z opns

## Zásobník
**SORTS**:
- elm, stack
**[[Varianty zoznamov#Zásobník|OPNS]]**
- Err
- Empty
- Push
- Pop
- Top
**EQNS**:
- Pop(Push) -> stack
- Top(Push) -> elm
- Pop(Empty) -> Empty
- Top(Empty) -> Err