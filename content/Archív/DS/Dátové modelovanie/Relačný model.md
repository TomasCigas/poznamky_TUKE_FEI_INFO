# Relačný model
Entity sú reprezentované vo forme tabuliek, riadkov a stĺpcov. Je pomerne blízko reálnej reprezentácii DBS.

**Tabuľka** -> entitná množina
**Riadok** -> konkrétna entita
**Stĺpec** -> atribút / modelovaná vlastnosť

## Pravidlá
1. Každá tabuľka má jednoznačný názov
2. Každý záznam tabuľky má rovnakú štruktúru
3. Každý stĺpec tabuľky má svoj názov (unikátny od ostatných v jednej tabuľke)
4. Na poradí stĺpcov nezáleží
5. Každý záznam v jednom stĺpci obsahuje hodnoty rovnakého atribútu
6. Každý záznam (riadok) v tabuľke zodpovedá jednému výskytu entity daného typu
7. Každý záznam je jednoznačne identifikovateľný v tabuľke primárnym kľúčom
	- Konvencia zadávania rozličných názvov primárnych kľúčov v rámci celej databázy
8. Na poradí záznamov nezáleží
9. Všetky hodnoty v zázname sú jednoznačne zadávané a závislé na primárnom kľúči


## Kľúč
Je atribút, alebo množina atribútov, ktoré **jednoznačne** identifikujú záznam tabuľky.

**Primárny kľúč**
- Každý záznam ho musí obsahovať
- Môže byť umelý
- Musí byť jednoznačný, ideálne minimálny

**Cudzí kľúč**
- odkazuje sa na primárny kľúč inej entity tabuľky