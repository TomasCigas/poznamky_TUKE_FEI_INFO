# Architektúry DBS
Architektúra vychádza zo štandardizovaného modelu *ANSI/SPARC*

## ANSI/SPARC
### Úrovne
#### Externá úroveň
Zjednodušuje pohľad jednotlivých používateľov.
[[Databázové systémy#Databázové systémy|Používateľ]] ľubovoľného typu môže používať na opis či zápis do pohľadov rôzne jazyky

#### Konceptuálna úroveň
Reprezentuje celý informačný pohľad na DBS.
Na konceptuálnej úroni sú pohľady definované tak, aká je skutočnosť.

#### Interná úroveň
Fyzické uloženie dát.

### Schémy
#### Externá schéma
Používateľské pohľady. Časť databázy pre vybranú skupinu používateľov, pri čom zvyšok im je neprístupný
#### Konceptuálna schéma
Štruktúra databázy, ktorá zakrýva detaily fyzickej štruktúry
#### Interná schéma
Fyzická štruktúra databázy, kompletné detaily umiestnenia dát, prístupová cesta k databáze

### Mapovanie
Proces transformovania požiadaviek medzi jednotlivými úrovňami.

### Nezávislosť údajov
Zmena schémy na jednej úrovni dat. systému nespôsobí to zmeny vo vyššej úrovni.
- Nezávislosť logických dát -> zmena konceptuálnej schémy
- Nezávisosť fyzických dát -> zmena internej schémy