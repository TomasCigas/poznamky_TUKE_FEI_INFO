# Syntaktická analýza
Proces, ktorého cieľom je zistiť, či slovo patrí jazyku a ak áno určiť jeho strom odvodenia.

**Metódy analýzy**:
- [[Zhora Nadol|*Zhora nadol*]] -> $S\Rightarrow ^*w$
- [[Zdola Nahor|*Zdola nahor*]] -> $w\Rightarrow ^*S$

**Najľavejšie odvodenie** ->vždy pri odvodzovaní sa vyberá neterminál najviac v ľavo
- produkuje vetné formy v tvate $uA\alpha$, kde $u$ je možné porovnávať so vstupným reťazcom $w$, teda nie je potrebné sa pri prvek kontrole po odvodení k $u$ vraciať
**Najpravejšie odvodenie** -> -//- v pravo
Tieto postupy je možné kombinovať.


## Teoretický model
### Zhora nadol
**Teoretický model syntatkického analyzátora zhora nadol** modeluje syntaktickú analýzu metódou [[#Zhora nadol|zhora nadol]], pri čom vychádza z nasledujúcich princípov:
- Automat bude v zásobníku symulovať pravú a ľavú stranu vstupného slova ($S \leftarrow w$)
- Na začiatku vloží automat do zásobníka začiatočný symbol
- Automat opakuje akcie do kedy sa nevyprázdni zásobník:
	- *Expanzia* -> ak sa na vrchu zásobníka nachádza neterminál, automat vyberie jedno z pravidiel, ktoré naň aplikuje
	- *Porovnanie* -> ak sa na vrchu nachádza terminál, porovnáva ho s aktuálnym symbolom na vstupe a ak sa zhoduje odstráni ho zo zásobníka, ak nie vstup neakceptuje
- Automat akceptuje vstupné slovo ak skončí s prázdnym zásobníkom

### Zdola nahor
**Teoretický model syntatkického analyzátora zdola nahor** je nedeterministický zásobníkový automat, ktorý sa konštruuje k danej gramatike, ale pracuje na inom princípe ako pri zhora nadol.
Funguje na princípe:
- začiatok -> prázdny zásobník
- Automat opakuje kým je možné realizovať nasledujúce akcie:
	- *Presun* -> presun vstupu do zásobníka
	- *Redukcia* -> viaže sa na pravidlo a mení ľavú stranu pravidla na pravú vo vstupnom, resp. produkčnom reťazci.
 
 Existuje ešte všeobecná metóda **posun-redukcia**, ktorá je rozšírením teoretického modelu:
 - Akcie:
	 - *Posun* -> uloženie vstupného symbolu
	 - *Redukcia* -> ak sa na vrchu zásobníka objaví handle, redukuje sa podľa gramatiky
	 - *Prijatie* -> úspešné ukončenie parsera
	 - *Error* -> funkcia na ošetrenie chyby
- handle sa vždy objaví na vrchu zásobníka


## (Ne)deterministická syntaktická analýza
Pri nedeterministickej syntaktickej analýze (NSA) nie je voľba pravidla predom určená (teda každý neterminál môže mať práve jedno pravidlo)

## Množiny FIRST, FOLLOW a PREDICT
### FIRST
Množina FIRST sa určuje pre každý *neterminál* a obsahuje terminály, ktoré sa nachádzajú ako prvé pri ľubovoľnom odvodení.

pre:
S -> aA
A -> b

sú:
FIRST(S) = {a}
FIRST(A) = {b}

ak FIRST obashuje $\epsilon$, tak sa prechádza na ďalší symbol:
S -> Aa
A -> b
A -> $\epsilon$

FIRST(S) = {b,a}
FIRST(A) = {b,$\epsilon$}


### FOLLOW
Množina FOLLOW sa určuje pre každý *neterminál* a obsahuje terminály, ktoré sa nacádzajú hneď za nimi.
Vo FOLLOW sa nenachádza $\epsilon$!

pre:
S -> Aa
A -> BD
B -> b
B -> $\epsilon$
D -> d
D -> $\epsilon$

si najprv určíme [[#FIRST]]:
FIRST(S) = {b,d,a}
FIRST(A) = {b,d,$\epsilon$}
FIRST(B) = {b,$\epsilon$}
FIRST(D) = {d,$\epsilon$}

Potom:

FOLLOW(S) = {$\epsilon$} -> nič za ním nikdy nebude následovať, keďže sa do ničoho neodvádza
FOLLOW(A) = {a}
FOLLOW(B) = {d,a} -> Keďže následovný neterminál D obsahuje $\epsilon$, tak dávame aj FOLLOW pravej strany, čo je FOLLOW(A)
FOLLOW(D) = {a} -> Za D sa nikde nenachádza nič, takže otáva len FOLLOW(A)

## Porovnanie [[Zdola Nahor|LR]] a [[Zhora Nadol|LL]]
LL|LR
--|--
realizuje sa najľavejšie odvodenie|relizuje sa opačné najpravejšie odvodenie
začína sa koreňom|končí sa koreňom
zásobník očakávaného vstupu|zásobník prečítaného vstupu
expanduje neterminály|redukuje neterminály
neterminály číta pri vyberaní zo zásobníka|neterminály číta po uložení do zásobníka
preorder čítanie stromu|postorder čítanie stromu
pravidlo je rozpoznané ľavou stranou a *k* symbolov z pravej strany|pravidlo je rozpoznané podľa všetkého z pravej strany a *k* symbolov, vyhľadávaných dopred

---
- [[Zhora Nadol]]
- [[Zdola Nahor]]
---