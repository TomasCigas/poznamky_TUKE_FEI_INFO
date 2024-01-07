***********
Konštrukcie sú diely jazyka, ako napríklad výrazy, deklarácie a pod.

*Vykonávanie programu* pozostáva zo sekvencie jednotlivých krokov výpočtu na počítači.
Tento výpočet je postupnosť podvýpočtov konštrukcií v danom programe.

Riadenie výpočtu vstupuje do konštrukcie akonáhle sa začne jej podvýpočet a vystupuje s jeho koncom.

Konštrukcie sa môžu líšiť [[#Tok riadenia|tokmi riadenia]], [[#Tok informácií|tokmi informácií]].
# Toky
## Toky riadenia
**Základné druhy**:
- *Zoradenie do postupnosti* (sequencing)
	- postupný vstup do konštrukcií zhora nadol (zľava doprava)
- *Prekladanie* (interleaving)
	- presúvanie medzi viacerými podkonštrukciami
- *Výber medzi alternatívami* (choice)
	- vstup len do jednej alternatívy, v prípade zlyhania sa vráti sa skúsi inú
- *Signalizovanie výnimočnej situácie* (exception raising)
	- prerušenie toku riadenia a vstup do uzatváracej podkonštrukcie
- *Iterácia* (iteration)
	- opakovaný vstup do rovnakej podkonštrukcie
- *Volanie procedurálnej abstrakcie* (procedural abstraction)
	- vstúpenie do konštrukcie, ktorá sa nachádza n inom mieste a po ukončení pokračuje od bodu aktivácie
- *Súbežné procesy* (concurrent processes)
	- delenie riadenia do viacerých vlákien
## Toky informácií
Základné druhy:
- *Výpočet hodnôt*
	- počítanie hodnôt vo výrazoch
- *Použitie vypočítaných hodnôt*
	- vstup informácie do konštrukcie
- *Účinok na pamäť*
	- alokovanie, či vloženie informácie do pamäte
- *Viditeľnosť* (scope)
	- väzby medzi podkonštrukciami, inak informácia v konštrukcii môže vstúpiť do jednej podkonštrukcie a potom do dalšej
- Odovzdávanie správ
	- konštrukcia získa informáciu, že jej kontext akceptuje správu a kontext získa informáciu uloženú v samotnej správe

# Špeciálne konštrukcie
Tieto konštrukcie slúžia na isté spôsoby vykonávania, ktoré nepodporuje prirodzená sémantika?
## Stop
Ide o okamžité zastavenie programu v danom bode.
Prechod pre tento príkaz neexistuje, nakoľko sa vykonávanie príkazu zastaví v konfigurácii. Formálne teda zapisujeme, že program neterminuje:
$$
\langle stop,s \rangle \rightarrow \bot
$$

Podľa [[Prirodzená sémantika|prirodzenej sémantiky]] sú príkazy **stop** a **while true do skip** sémanticky ekvivalentné, nakoľko sa prirodzená sémantika pozerá len na (ne)termináciu a nie jeho dôvod.

## Or
Or zavádza nedeterminizmus do jazyka. Teda tento príkaz vyberie náhodne, ktorý z dvoch poskytnutých možností sa vykoná:
$$
S \ \texttt{or}\ S
$$
V prípade [[Prirodzená sémantika|prirodzenej sémantiky]] nedokážeme presne určiť ako bude program pokračovať, nakoľko neobsahuje prostriedky, ktorými by dokázala definovať jednoznačnú sémantiku pre nedeterministické programy.
## Par
Par zavádza do jazyka súbežné vykonávanie príkazov. V tomto prípade ide o vykonanie oboch príkazov, avšak v neznámom poradí:
$$
S\ \texttt{par}\ S
$$
Jednotlivé príkazy sú atomické, teda prvý  sa musí vykonať celý dokým sa vykoná ten druhý. [[Prirodzená sémantika|Prirodzená sémantika]] opäť neposkytuje jednoznačný význam pre takéto súbežné vykonávanie, nakoľko nevieme určiť jednoznačné poradie príkazov

## Bloky a deklarácie

Bloky sú časti programu viditeľnosťou oddelené od vyššieho bloku. Inak povedané blok vidí premenné vyššieho bloku, avšak vyšší blok nevidí premenné nižšieho bloku:
![[bloky.excalidraw]]
Najvyšší možný blok je hlavné telo programu.

Blok sa skladá z **premenných** a **tela bloku**.

Blok sa delí na:
- pomenovaný - môžeme sa naň odvolávať viacero-krát, takýto blok nazývame [[#Procedúry|procedúra]]
- nepomenovaný

Produkčné pravidlo bloku je:
$$
begin\ D;S\ end
$$
, kde D sú **deklarácie** a S sú príkazy, teda **telo** bloku.

Samozrejme blok nemusí obsahovať žiadne deklarácie (technicky aj žiadne príkazy, ale potom je blok zbytočný).

## Procedúry
Procedúra je pomenovaný [[#Bloky a deklarácie|blok]], na ktorý sa môžeme odvolávať v procese programu (je to teda funkcia či metóda závisiac od programovacieho jazyka).

Deklarácia procedúry je teda:
$$
	D_p ::= \texttt{proc}\ p\ \texttt{is}\ S;D_p\ |\ \epsilon
$$

Táto deklarácia sa nachádza hneď po deklarácii premenných bloku:
$$
\texttt{begin}\ D\ ;\ D_p\ ; S\ \texttt{end}
$$
Na zavolanie procedúry sa používa funkcia $\texttt{call}\ p$.


---
