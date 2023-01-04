***********
Existuje viacero vyhľadávacích problémov (viď kapitoly).

**Agent** - entita, ktorá vníma a reaguje na zmeny v priestore pomocou senzorov a ovplivňuje prostredie pomocou akcií

**Typy agentov podľa racionality** (podľa užitku a penalizácie):
- **Reflexný agent**: rozhoduje sa na základe momentálneho stavu
- **Cieľový agent**: rozhoduje sa nazáklade momentálneho cieľa
- **Užitkový agent**: rozhoduje sa na základe užítku, ktorý dosiahne ďalším krokom

**Agentový priestor** - priestor, v ktorom sa agent pohybuje (vykonáva akcie)
- signle-agent vs multi-agent
	- kooperatívny vs kompetetívny
- dynamickosť:
	- statický - priestor sa bez agenta nemení
	- semi-dynamický - priestor sa nemení časom, ale nastávajú javy dôsledkom akcie agenta
	- dynamický - priestor sa mení aj časom
- diskrétnosť:
	- diskrétny - má konečný počet možných akcií
	- spojitý - nemá konečný počet akcií
- kompletnosť (z pohľadu agenta):
	- úplný
	- čiastočný

Interakcia agenta s prostredím funguje na základe logickej tabuľky (podľa ktorej sa agent rozhoduje)
![[agent_priestor.excalidraw]]

# Stavový priestor
Uzol = stav
Hrana = jav (akcia agenta)

Obvykle sa stavový priestor reprezentuje ako graf. Keďže kvôli veľkému množstvu stavov môže byť graf ohromný, preto ho obvykle reprezentujeme vo forme *stromu* (necelého). A nad ním môžeme vykonávať mnoho algoritmov.

Stromové vyhľadávanie spočíva vo vytvorení stromu a následnom prehľadávaní určitým spôsobom.
Tento strom predstavuje súslednosť akcií agenta (hrany) a stav agentového priestoru (uzly).
Strom expandujeme dokým nenájdeme riešenie.

Vyhľadávanie v grafe vs strome:
- pokiaľ sa v grafe nachádza cyklus môžeme sa zacykliť pri tvorbe stromu
	- riešime zásobníkom navštívených stavov







---
- [[Problém bez informácií]]
- [[Problémy s informáciami]]
- [[Identifikačné problémy s ohraničienami]]
---