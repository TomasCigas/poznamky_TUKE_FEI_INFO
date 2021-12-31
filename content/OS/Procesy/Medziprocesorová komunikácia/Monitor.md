# Monitor
**Monitor** je konštrukcia programovacieho jazyka, ktorá poskytuje ekvivalentnú funkciu [[Semafóry|semafórov]].
- teda je to *softvérový modul*

- implementuje sa, pretože implementácia semafórov môže byť komplikovaná

Pozostáva z:
- lokálnych dát
- inicializačnej sekvencie
- minimálne jednej procedúry

Hlavné charakteristiky:
- lokálne dáta sú dostupné iba procedúrami
- proces vstupuje do monitora aktiváciou jednej z jeho procedúr
- v danom čase sa môže vykonávať len jeden proces

Prostriedky synchronizácie:
- [[Semafóry#Podmienená premenná Conditional Variable|Podmienené premenné]]
- Funkcie nad podmienenými premennými
	- **cwait($c$)** -> pozastavenie vykonávania procesu na premennej $c$
	- **csignal($c$)** -> obnovenie vykonávania niektorého procesu na premennej $c$