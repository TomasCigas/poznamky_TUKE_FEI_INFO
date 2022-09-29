# Analýza

**Syntak** môže byť:
- *konkrétna* -> slúži na lexikálnu a syntaktickú kontrolu programov
	- určuje či znaky a ich reťazce patria konkrétnemu jazyku
	- určuje strom odvodenia pre každý akceptovaný program
	- je špecifikovaná gramatikami a zapísaná pre každý neterminálny symbol
	- je jednoznačná, prípadne sa pridávajú pravidlá
- *abstraktná* ->
	- zaoberá sa štruktúrou programu
	- slúži pre účely formálnej sémantiky
	- venuje sa len štruktúre, ktorá je:
		- nepriradená konkrétnemu jazyku

## Chyby
Pri analýze zisťuje analyzátor druh a počet chýb a podľa typu, druhu a vážnosti vypíše chybu.

**Druhy chýb**:
- **Lexikálna chyba** 
	- natane, keď symboly na vstupe nie je možné premeniť na ktorýkoľvek z Tokenov
- **Syntaktická chyba**
	- nastan, ak nie je dodržané niektoré z pravidiel, ktoré sú určené gramatikou
- **Sémantická chyba**
	- naznačuje chybu v interpetovaní vstupu (napr. nedeklarovaná premenná, nesprávny typ ...) 
- **Logická chyba**
	- táto chyba neopisuje zlyhanie analýzy, či prepisu, ale chybu samotného vstupu -> vstup nemá alebo stráca logický význam v niektorých/všetkých prípadoch
 
 Účinné zotavenie z chyby spočíva v správnej definícii [[Gramatika|gramatiky]]:
 - každý terminálny symbol by sa mal v gramatických pravidlách vyskytovať iba raz
 - všetky bloky programu by mali byť jednoznačne oddelené

### Metódy zotavenia z chyby
Slúžia na poskytnutie detailov chyby používateľovi spolu s reakciami, ktoré by mal program uskutočniť

**Metódy**:
- **Panic Mode Recovery**
	- hodí výnimku a ukončí program
	- najzákladnejší a najjednoduchší
	- *Výhody*:
		- ľahká implementácia
		- jednorázové a rýchle
	- *Nevýhody*:
		- môže byť preskočený dlhý sled jednotiek
- **Statement Mode Recovery**
	- spočíva v zmene tabuľky prediktívnej analýzy pomocou ukazovateľa na chybu (resp. rutinu)
	- chybové rutiny menia, vkladajú či odstraňujú symboly zo vstupu a posyktujú hlásenie
	- *Výhody*:
		- realizuje sa lokálna úprava na vstupe
	- *Nevýhody*:
		- zvykne byť náročná
- **Error Productions**
	- stará sa o bežné chyby a zvykne ich opravovať
	- pokiaľ nastane chyba, vstup sa interpretuje korektne vďaka týmto "nádstavbám"
- **Global Correction**:
	- analyzátor pri chybnom vstupe poznmení celý vstup na ten s najbližšou zhodou
	- najbližšia zhoda obashuje najmenší počet zmien na vstupe (resp. tokenov)
	- nie je praktická pre časovú a priestorovú komplexitu

**Zotavenie v prípade lexikálnej chyby**:
 - typicky sa využíva [[#Metódy zotavenia z chyby|panic mode]]
 - ľahká implementácia a jednoznačný koniec (bez zacyklenia)
 - preskočí sa koniec, kde sa môžu nachádzať ďalšie chyby
**Zotavenie v prípade sémantickej chyby**:
- môžu byť [[#Metódy zotavenia z chyby|panic mode, statement mode recovery alebo error correction]]
- obvyklé chyby:
	- nekompatibilný typ operátorov -> cast do požadovaného typu
	- nedeklarované premenné -> deklaruje sa 
	- nezhoda skutočných a formálnych argumentov

**Základné východisko zotavenia** je *definícia množiny symbolov* a funkcie *error* a *check*

## Údajové štruktúry analyzátora

Analýza potrebuje na svoju funkciu niektoré [[Údaje a údajové štruktúry|údajové štruktúry]].

### Tabuľka symbolov
Pomocou nej môžeme jednotlivým menám priradzovať ich atribúty, zabezpečuje vloženie a efektívne vyhľadávanie atributových záznamov.

**Implementácia**:

Typ|Ukladanie|Vyhľadávanie
--|--|--
Neusporiadaný zoznam|O(1)|O(n)
Usporiadaný zoznam|O(n)|O(log(n))
BNS|O(log(n))|O(log(n))
Hašovacia tabuľka|max - O(n)|max - O(n)

### Pamäť pre premenné
Rezervovaná oblasť pre proces obsahuje samotný kód a preň potrebné premenné.
Oblasť, ktorá je pridelená premennej je daná:
- **Adresou** -> začiatok údaju o premennej
- **Typom** -> potrebná dĺžka, pre daný typ premennej

Lokálne premenné spolu s príslušnými informáciami tvoria **aktivačný záznam**.

---
- [[Syntaktická analýza]]
- [[Lexikálna analýza]]
- [[Sémantická analýza]]
---