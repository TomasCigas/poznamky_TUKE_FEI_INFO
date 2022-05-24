# Systém riadenia bázy dát
Softvér, pomocou ktorého sa vykonáva riadenie nad databázami.

## Základná funkcionalita a účely
**Funkcionality:**
- Definovanie databázy - špecifikácia dátových typov a štruktúry
- Konštrukcia databázy - proces ukladania dát na nejaké pamäťové médium
- Aktualizácia a manipulácia údajov v databáze

**Účely:**
- Cielený výber údajov z databázy

## Komponenty
- Údaje
	- trvácne
	- integrované
	- štruktúrované
	- zdieľané
- Hardvér
- Softvér
- Postupy:
	- pravidlá pre návrh
- Používatelia

## Údaje v súboroch
Pred DBS sa údaje ukladali do súborov, čo spôsobovalo:
- Redundanciu a inkonzistenciu údajov:
- Komplikovaný prístup k údajom
- Izolácia údajov
- Atomicita zmien
	- zlyhanie systému počas zmeny ponechá údaje v nestabílnom stave
- Súbežný prístup k údajom
	- podobne ako pri atomicite, nekontrolovaná súbežnosť
- Bezpečnosť
	- kontrola používateľov a ich obmedzenie
- Malý výkon

Všetky tieto problémy rieši DBS, stačí len vedieť dopitovací jazyk tejto DBS.

## Implementácie
- PostgreSQL
	- používaný nami, open-source
- Sqlite
- MySQL (MariaDB, Percona)
- MS-SQL, Oracle

## SQL
Začiatok 1970 rokov -> vyvynutý firmou IBM.
Začiatok 1980 rokov -> existuje množstvo SRBD, kde každý používal vlastny dopitovací jazyk

**SQL** je štandardizovaný jazyk na manipuláciu s dátami.

**Typy príkazov**:
- **DDL** (Data Definition Language)
	- definícia štruktúry databázy (CREATE, DROP, ALTER, TRUNCATE)
- **DML** (Data Manipulation Language)
	- manipulácia s údajmi (SELECT, INSERT, UPDATE, DELETE)
- **DCL** (Data Control Language)
	- riadenie prístupu (GRANT, REVOKE)
- **TCL** (Transaction Control Language)
	- riadenie transakcií (COMMIT, ROLLBACK, BEGIN WORK)

