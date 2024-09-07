*********************************
Používa sa na procesovanie veľkého množstva dát (petabyty) . Jedno zariadenie nezvládne spracovávať všetky dáta, musíme preto distribuovať a paralelizovať ich spracovanie. Snažíme sa dosiahnuť vysokú rýchlosť spracovania.

**masívny paralelizmus** - rovnaká operácia na viacerých zariadeniach. 

- Algoritmus, ktorý bol vytvorený na spracovanie veľkých dát (prišiel s tým Yahoo)
- Distribuovaný file systém od Hadoo
- Google prišiel s map reduce, ale odobral si file systém od Hadoo
- Vyplýva z funkcionálneho prog. - Lisp
- poskytuje:
	- automatickú paralelizáciu a distribúciu
	- I/O scheduling - vhodné použitie zápisov a čítania (ďaleké I/O chceme nahradiť lokálnym - cache)
		- load balancing
		- optimalizáciu siete a dát
	- Správa chyby
		- správa chyby zariadenia
- škálovanie do šírky - máme veľké množstvo bežných serverov, nie malé množstvo špecializovaných
	- rovnaký algoritmus na všetkých serveroch

Na správnu funkcionalitu Map Reduce potrebujeme **Distribuovaný file systém** (GFS, [[#HDFS]]).


# Typické problémy
- čítanie veľa dát
- *Map* - extrahovanie informácií z dát
- shuffle & sort - rekonfigurácia (usporiadanie) dát na sumarizáciu výsledku
- *Reduce* - agregácia, sumerizácia, filtrácia alebo transformácia informácie
- Zápis
*Map* a *Reduce* replikujeme na viacero zariadení

# Workflow
#add_pic
- Worker robí (vertikálne) stále to isté
- môžeme si to predstaviť ako key-value storage
- výstupné dáta sú už automaticky distribuované

# Workers
Map a Reduce sú [[#Workflow|distribuované]], teda pokiaľ chceme spracovávať viacero dát, pridávame len mapperov a reducerov.
Vďaka tomu nemusíme riešiť multithreading, nakoľko každý mapper a reducer je jednovláknový program, ktorý je deterministický - determinizmus dovoľuje reštart zle ukončenej práce
Mappre a Reducre fungujú nezávislo od seba.

**Mapper** - Číta vstupnú dvojicu $<K,V>$ a výstupom je tiež $<K',V'>$
**Reducer** - príjma dáta od mappera a agreguje $K$ a $V$

Fungujú vďaka **shardovaniu databázy**, ktorá funguje na báze key-value storage, ktorá sa automaticky stará o shuffle & sort.
# Input data
Chceme aby vstupné dáta boli blízko workerov aby sme neposielali petabyty po sieti (zahĺtenie) - najlepšie na jednom racku.
Vstupné dáta sú **nemenné**.

## Lokálna optimalizácia
#add_info 



## HDFS
Koncepty:
- máme 128MB bloky
- Data nody - ukládanie a získavanie blokov
- Name nody - metadáta o súboroch
![[Drawing-1714631022947.excalidraw]]
Operácia HDFS:
#add_pic 
- Operáciu write si musíme rozmyslieť - či ju chceme použiť aj na úpravu súborov

Rack awarness - vieme v ktorých rackoch sú ktoré nódy
- pokiaľ je to teda vhodné, chceme ukladať dátové nódy do jedného racku
	- môžeme robiť operácie len na jednom racku, teda v lokálnej sieti
![[Drawing-1714632020852.excalidraw]]

# Fault Tolerance
Pokiaľ vypadne [[#Workers|worker]] tak len spustíme jeho proces ešte raz na inom workerovi, prípadne ho reštartujeme.

Pokiaľ vypadne master tak musíme vrátiť systém podľa logov do funkčného stavu.

**Redundantné vykonávanie** - vykonávame rovnaké dáta na viacerých workeroch, kvôli spoľahlivosti - pokiaľ mi niečo padne, tak ďalšie stroje to vykonajú. 
**Preskakujeme zlé záznamy** - preskakujeme dáta, ktoré worker nevie prečítať.



*********************************