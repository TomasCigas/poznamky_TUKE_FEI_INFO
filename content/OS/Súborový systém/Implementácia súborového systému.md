# Implementácia súborového systému
Potrebujeme nejakým spôsobom zapisovať naše [[Adresáre#Štruktúra adresárov|komplexné]] spôsoby zápisu na [[Disky|disky]].

## Všeobecné princípy
Dochádza k abstrakcii zariadenia:
Cylindre, hlavičky, sektory -> Zoznam blokov -> Zoznam bajtov.

Konkretizácia [[Súbory|súboru]]:
Súbor -> zoznam záznamov -> zoznam bajtov

Došlo nám k "stretu" definícií

**Súborový systém** je spôsob mapovania *súborového* zoznamu bajtov -> zoznamu bajtov *zariadenia*.

Konceptuálne riešenie je teda:
![[concept_filesystem.excalidraw]]

Máme mnoho rôznych súborových systémov, ktorých rozlišnosti potrebujeme pred používateľom (resp. programom) zakryť (kvôli všeobecnosti).

Samotná implementácia spočíva v "on-disk" a "in-memory" dátových štruktúr.

### Implementácia adresárov
- **Zoznam**
	- lineárna štruktúra
	- neefektívna pri veľkom množstve
- **Hash tabuľka**
	- musíme definovať veľkosť na začiatku

### Správa voľného miesta
Potrebujeme znovuvyužiť uvoľnené miesto

**Prístupy**:
- Bitový vektor
- Spojkový zoznam
- Grupovanie
- Počítanie

## Konkrétne prípady
### FAT
Štandardný model:
![[FAT_FS.excalidraw]]



### UNIX systém
Štandardný model:
![[UNIX_FS.excalidraw]]
- **Boot blok** + **Superblok** -> kód a dátové štruktúry určujúce parametre súborového systému
- **i-nody** -> tabuľka i-nodov jednotlivých súborov
