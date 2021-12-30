# Historické prístupy

## Oblasti s pevnou veľkosťou
- veľkosť oblasti je predurčený
- môže deliť celkovú pamäť na partície rovnakej alebo rôznej veľkostí

Problémy, ktoré môžu nastávať
- **interná fragmentácia** -> procesy len zriedka využívajú celú partíciu (môže sa vylpšiť rôznou veľkosťou partícií)
- **prekrývanie** -> môže nastať, že máme proces vyplňujúci viac ako jednu partíciu, v tomto prípade bola časť kódu uložená do trvalej pamäte a postupne robil program výpočty, čo komplikuje prácu programov a spomaľuje ich

- pripisovanie programov do pamäte môžeme robiť dvoma spôsobmi:
![[proc_queue.excalidraw]]

## Oblasti s premenlivou veľkosťou
- veľkosť oblasti sa mení počas výpočtov

Problémy, ktoré môžu nastávať:
- **externá fragmentácia** -> pri konštntnom alokovaní a dealokovaní dochádza k tvorbe "dier" v našej pamäti
- **zhusťovanie** -> je riešenie externej fragmentácie, ide o presúvanie jednotlivých procesov v pamäti na voľné miesta a teda zbavovanie sa naších "dier", ide však o drahú činnosť a snažíme sa jej vyhnúť
- jednotlivé procesy sa môžu umiestniť do pamäte 3 spôsobmi:
	1. **First fit** -> prvé voľné miesto, vytvára fragmentáciu na začiatku pamäte
	2. **Next fit** -> alokácia hneď za posledným alokovaným priestorom, veľká fragmentácia, nie stále funguje
	3. **Best fit** -> najlepšie možné miesto, môže trvať dlho kým sa však nájde

### Blokový systém
(Buddy system)
- dostupnú pamäť ktorú mám k dispozícii delím na polovicu, dokým nedostanem minimálny možný blok pamäte
- pri dealokovaní dochádza ku spájaniu prázdnych menších blokov pamäte do väčšej
- tento systém zabraňuje externej fragmentácii a minimalizuje internú fragmentáciu

## Stránkovanie
- operačná pamäť je rozdelená na **rovnako veľké** a pomerne malé bloky [[#Oblasti s pevnou veľkosťou|pevnej dĺžky]] (stránky) .
- každý program má svoju (logickú) pamäť rozdelenú na bloky takej istej veľkosti 

- operačný systém potom alokuje časť programu do viacerých stránok
![[strankovanie.excalidraw]]

- problém je, že [[Pojmy#Logická adresa|logická]] a [[Pojmy#Fyzická adresa|fyzická]] adresa nie je rovnaká, takže potrebujeme tabuľku stránok, ktorá obsahuje na akom mieste sa nachádzajú jednotlivé procesy

Prevod logickej na fyzickú adresu:
![[strank_convert_log_fyz.excalidraw]]
- offset je poloha adresy od začiatku predurčenej stránky

## Segmentácia
- bloky dát sú [[#Oblasti s premenlivou veľkosťou|premenlivej]] dĺžky
- program je rozdelený na niekoľko segmentov
	- sú viditeľné pre používateľa
	- sú rozdelené logicky (napr. kód a dáta)
- podobne ako pri [[#Stránkovanie|stránkovaní]] definujeme segmenty tabuľkou

Prevod logickej na fyzickú adresu
![[segm_conv_log_fyz.excalidraw]]

- tabuľka segmentov je zložitejšia, pretože tam ukladáme a ich dĺžku
- báza je adresa začiatku segmentu, pri čom dokážeme vďaka dĺžke aj určovať, či sme presiahli dĺžku segmentu pomocou komparátora, podobne ako pri: [[Správa pamäte#Hardvérový mechanizmus|hardverovom mechanizme]].