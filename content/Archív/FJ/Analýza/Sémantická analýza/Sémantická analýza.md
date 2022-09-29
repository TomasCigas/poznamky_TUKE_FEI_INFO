# Sémantická analýza
[[Syntaktická analýza]] sa vyvoláva za účelom **sémantického spracovania** -> teda čo jednotlivé slová/vety znamenajú a aké príkazy majú vykonávať.

**[[Gramatika#Kompilátory|Sémantické podprogramy]]** -> podprogramy, ktoré sa vyvolávajú sémantickým analyzátorom (ako integrovaná súčasť jazykového procesora), za účelom vykonávajú interpretáciu programu na základe jeho syntaktickej štruktúr.

**Všeobecný prístup (koncepcia)**:
- syntaktický analyzátor reprezentuje program v tvare [[Gramatika#Strom odvodenia|stromu odvodenia]], alebo tzv. *abstraktného syntatkického stromu* (AST)
	- rozdiel medzi stromom odvodenia a AST:
![[ASTvsSO.excalidraw]]
- jednotlivým vrcholom AST sú pridelené jednotlivé sémantické atribúty
	- sémantický atribút môže byť napr. názov, adresa, typ premennej, hodnota, konštanta a i.

Sémantický analyzátor zisťuje akým spôsobom medzi sebou sémantické podprogramy budú komunikovať a aký bude kedy použitý.

Syntaktický analyzátor do syntaktickej reprezentácie tzv. **akčné symboly**, ktoré slúžia na lepšiu interpretáciu kódu, na rozpoznanie označujeme '#' napr.:
$$
\begin{align}
<príkaz> \rightarrow if <výraz> then <príkaz> \\
<príkaz> \rightarrow if <výraz>#if_podmienka then <príkaz>#if_koniec
\end{align}
$$
tento konkrétny slúži na identifikovanie if podmienky a pokiaľ ju nesplníme, tak nech program *skočí* na if_koniec.
Podľa toho na aký akčný symbol analyzátor narazí, taký *sémantický podprogram* bude spustený.

**Sémantický zásobník** je údajová štruktúra obsahujúca *sémantické atribúty* slúžiace na komunikáciu medzi jednotlivými sémantickými podprogramami. Podľa toho môžeme SZ asociovaný s podmienkou IF naplniť akčnými symbolmi \#if_podmienka a \#if_koniec. Prípadne pri asociácii môže obsahovať adresu, kam sa má daná premenná uložiť. Toto povoľuje kvázi komunikáciu medzi sémantickými podprogramami.

**Zhrnutie**:
- definícia SA, koncepcia SA
- vstup, výstup SA
- medzikód, význam a formy
- AST, postfix, jazyk štvoríc
- sémantické podprogramy
- sémantický zásobník a väzba na syntaktický zásobník
- rozdiel SA zhora nadol a zdola nahor	

## Sémantické spracovanie pri syntaktickej analýze [[Zhora Nadol]]
Do SZ sa budú ukladať okrem terminálov a neterminálov aj akčné symboly, spolu so špeciálnym symbolom EOP (end of production), ktorý reprezentuje pravý koniec pravidla, spolu so štyrmi indexmi:
- $l$ -> ľavá strana aktuálne spracovaného pravidla
- $p$ -> pravá strana -//-
- $a$ -> aktuálne spracovaný symbol (vrch zásobníka syntaktického analyzátora)
- $v$ -> prvý voľný záznam v sémantickom zásobníku

## Sémantické spracovanie pri syntaktickej analýze [[Zdola Nahor]]
Odlyšuje sa od [[#Sémantické spracovanie pri syntaktickej analýze Zhora Nadol|LL]] analýzy dvomi rozdielmi:
- akčné symboly môžu byť uložené len na koniec pravej strany pravidla (pretože konkrétne pravidlo je zistené, až keď jeho celá pravá strana sa nachádza v syntaktickom zásobníku)
- ovládanie sémantického zásobníka je o mnoho jednoduchšie, paralelne pracuje so syntaktickým zásobníkom

---
- [[Medzikód]]
---