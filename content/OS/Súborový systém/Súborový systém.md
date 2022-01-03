# Súborový systém
**Súbor** je počítačový zdroj, ktorý slúži na záznam dát. Je primárne určený svjoím menom.

Môže nastať problém v [[Klasifikácie#Podľa počtu paralelne pracujúcich používateľov|viacpoužívatelských]] a [[Klasifikácie#Počtu paralelne bežiacich úloh|viacúlohových]] OS. -> môže dôjsť ku konkurovaní dvoch úloh.
Riešenie tohto problému je **zamykanie súborov**

## Atribúty súboru
- Meno
- Identifikátor
- Typ
- Umiestnenie
- Veľkosť
- Prístupové práva
- ID používateľa (tvorcu)
- Dátum a čas

## Základné operácie súborov
- Tvorba
- Zápis
- Čítanie
- Zmena aktuálnej pozície
- Zmazanie
- Zmena veľkosti
## Typy súborov
- Executable (každý OS)
- Adresáre
- Aplikačne špecifické
	- prípony
	- _magické číslo_
- Textové / Binárne

## Interná štruktúra súbor. systému
[[Operačné systémy|OS]] musí obsahovať programový kód na správu štruktúry.
Ide predovšetkým o definíciu (mimo execute).

## Metódy prístupu k dátam
### Sekvenčný
Čítame/Píšeme na ďalšie miesto, prípadne ho preskakujeme.

### Priamy
Čítame/Píšeme na presne dané miesto

### Odvodené od priameho

## Spôsoby organizácie záznamov
- Logická štruktúra
- Fyzická štruktúra
- Mapovanie
- Kritériá:
	- prístupová doba
	- zložitosť aktualizácie
	- réžia ukladania
	- jednoduchosť obsluhy
	- spoľahlivosť

- Hromada
- Sekvenčný súbor
- Indexovaný súbor
- Index-sekvenčný súbor
- Hašovaný súbor
- B-stromy


---
- [[Adresáre]]
- [[Ochrana súborov]]
- [[Implementácia súborového systému]]
---