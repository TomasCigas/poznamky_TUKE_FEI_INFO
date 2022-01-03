# Ochrana súborov

Poznáme:
- **Ochrana pred poškodením (protection)**
- **Ochrana pred zneužitím (security)**

## Typy prístupu (security)
Teda aké práva môžeme nadobudnúť:
- Čítanie
- Zápis
- Execute
- Pridávanie
- Mazanie
- Výpis
 
 ## Riadenie prístupu
 ### Všeobecný princíp
 Prístup je zrealizovaný na základe autentifikácie -> autorizácie
 
 ### Technická realizácia
 #### Access-control list (ACL)
 Existuje tabuľka používateľov s právami.
 
 ACL je štruktúra premenlivej dĺžky -> môže byť veľmi veľká s veľkou réžiou spracovania. MôŹeme to riešiť:
- **Kompaktnou verziou** -> UNIX/Linux práva
- **Kombinovanou verziou** -> Linux: acl, getfacl, setfacl

## Obnova (recovery)
Spočíva v nájdení chýb v súborových systémoch a ich nápravu.

**Spôsoby**:
- Zálohovanie a obnova zálohy
- Consistency checking (fsck)
	- kontrola konsistnecie súborového systému
- Žurnálovacie FS (NTFS, ext3)
	- založené na transakciách
	- pri zápise sa vykoná veľa operácií a čo sa vykonalo