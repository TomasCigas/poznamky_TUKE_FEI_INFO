# Systém riadenia bázy dát
Softvér, pomocou ktorého sa vykonáva riadenie nad databázami.

## Základná funkcionalita a účely
**Funkcionality:**
- Definovanie databázy
- Konštrukcia databázy
- 

**Účely:**

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
- 
- Atomicita zmien
- Súbežný prístup k údajom
- Bezpečnosť

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
- DDL -> definícia štruktúry databázy (CREATE, DROP, ALTER, TRUNCATE)
- DML -> manipulácia s údajmi (SELECT, INSERT, UPDATE, DELETE)
- DCL -> riadenie prístupu (GRANT, REVOKE)
- TCL -> riadenie transakcií (COMMIT, ROLLBACK, BEGIN WORK)

