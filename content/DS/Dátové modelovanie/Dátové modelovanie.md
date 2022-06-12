# Dátové modelovanie
Jedná sa o analýzu informácií v systéme. Kladie sa dôraz na logické entity a ich závislosti.

**Dátový model** -> množina pojmov a pravidiel opisujúca štruktúru databázy.

## Proces projektovania databáz
Etapy:
- **Systémová analýza** predmetnej oblasti a slovný opis databázy
- **Konceptuálne projektovanie** -> návrh [[Databázové systémy#Údajový model|konceptuálneho]] modelu
- **Voľba [[Systém riadenia bázy dát|SRBD]]**
- **Implementačné projektovanie** -> návrh [[Databázové systémy#Údajový model|logického]] modelu 
- **Fyzické projektovanie** -> reálne vytvorenie objektov v databáze

## Integrita údajov v databáze
Databáza sa musí starať, aby boli údaje konzistentné a neporušené.
DBS poskytuje [[Systém riadenia bázy dát#SQL|mechanizmy]] na zabezpečenie integrity údajov.

**Typy**:
- Doménová -> definícia povolených hodnôt v stĺpcoch => rovnaká štruktúra záznamov
	- Hodnoty musia byť *atomické* a z definovanej domény
- Entitná -> zabezpečenie primárneho kľúča => jednoznačná identifikácia záznamov
- Referenčná -> zabezpečuje existenciu a integritu cudzieho kľúča => správnosť vzťahov
	- *Kaskádny prístup* -> ak sú zmazané riadky v tabuľke, sú zmazané aj riadky v odkazovaných tabuľkách
	- *Restrikčný prístup* -> záznam nemôže byť zmazaný, ak naň existuje referencia
	- *Nulitný prístup* -> cudzí kľúč sa nastavý na null

## Normalizácia
Slúži na ukladanie dát bez duplicít a zabráňuje anomáliám pri manipulácii s údajmi.

### Normálne formy
Jedná sa o sadu pravidiel, kde každá úroveň musí spĺňat svoje a o úroveň nižšie pravidlá.

**1 NF** -> Každý atribút obsahuje iba atomické hodnoty ( každý atribút obashuje len jednu hodnotu )
**2 NF** -> Každý nekľúčový atribút závisí na primárnom kľúči ( pri zložených kľúčoch, ak niektorý atribút je závislý len na jednej časti kľúča )
**3 NF** -> Atribúty sú navzájom nezávislé (okrem primárneho)

Dôsledok použitia normalizácie je rozdelenie údajov do viacerých tabuliek.

---
- [[Entitno-Relačný model]]
- [[Relačný model]]
---