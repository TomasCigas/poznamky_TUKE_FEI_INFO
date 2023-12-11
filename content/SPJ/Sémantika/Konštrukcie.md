***********
Konštrukcie sú diely jazyka, ako napríklad výrazy, deklarácie a pod.

*Vykonávanie programu* pozostáva zo sekvencie jednotlivých krokov výpočtu na počítači.
Tento výpočet je postupnosť podvýpočtov konštrukcií v danom programe.

Riadenie výpočtu vstupuje do konštrukcie akonáhle sa začne jej podvýpočet a vystupuje s jeho koncom.

Konštrukcie sa môžu líšiť [[#Tok riadenia|tokmi riadenia]], [[#Tok informácií|tokmi informácií]].
# Toky riadenia
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
# Toky informácií
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




---
