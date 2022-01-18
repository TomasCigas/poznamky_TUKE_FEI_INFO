# Sekvenčné logické obvody
Výstup závisí od kombinácie vstupov a vnútorného **stavu** => je závislý od *sekvencie* vektorov na vstupe, na to si však musí systém pamätať aký druh vstupu už doň bol zapísaný, to sa deje pomocou:
- **Preklápací obvod** -> uchováva jednobitovú informáciu
	- riadené hladinou (latch) a hranou (flip-flop)
	- a/synchrónne
	- D, T, SR, JK
- **Bistabilný obvod** -> uchováva 1 bit informácie pomocou stavovej premennej Q (resp. Q')

**Stav** -> je konfigurácia vstupných a vnútorných veličín

**Metastabilný stav** -> stav, kde výsledné preklopenie obvodov je náhodné:
- Bistabilné zariadenia -> dva stabilné stavy a jeden metastabilný
- Flip-flop -> -//-, v metastabilnom stave je ťažko určiť ako dlho tam ostane

## SR
Set/Reset -> uchováva jeden bit informácie o stave systému a je možné zmeniť jeho hodnotu na default (často 0)

## D FF
D Flip-Flop

Vzorkuje D pri prechode hodinami (clk) z jednej úrovne na druhú

## Konečno-stavové automaty
Obsahujú **stavový register** na uchovávanie stavu, ktoré sa môžu preklápať pri zmene CLK a **kombinačnú logiku**, ktorá je zodpovedná za budenie signálov a zmenu vnútorného stavu, teda aj zmenu na výstupe.

**Automat Moore** -> výstup je závislý len od vnútorného stavu
**Automat Mealy** -> výstup je závislý ako od vnútorného stav, tak aj od vstupu

**Syntéza** KSA:
1. Urč vstupy a výstupy
2. Načrtni graf prechodov
3. Zostav tabuľku prechodov a výstupov
4. Zvoľ kódovanie
5. Podľa typu KSA:
	- Moore -> aplikuj zvolené kódovanie na tabuľku prechodov a potom na tabuľku výstupov
	- Mealy -> aplikuj zvolené kódovanie na tabuľku prechodov a výstupov
6. Odvoď budiace a výstupné funkcie
7. Nakresli schému

## Časové charakteristiky
Pre hranou riadený PO:
- pre správnu činnosť PO je nutné dodržať niektoré dynamické parametre:
	- doba predstihu, presahu
	- minimálna strmosť hrany CLK impulzu a minimálna doba jeho trvania
	- ich nedodržanie vedie k metastabilnéu stavu, kde sú preklopenia náhodné

