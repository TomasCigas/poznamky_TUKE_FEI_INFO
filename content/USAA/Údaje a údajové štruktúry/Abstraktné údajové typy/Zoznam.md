# Zoznam
Zoznamy, ich varianty, grafy, stromy...

Berie sa to ako **konečná** postupnosť položiek rovnakého typu.

**Základné operácie** nad ADT zoznamom sú:
- Insert
- Delete
- Member
- Cat
- Cut

**Implementácie zoznamu**:
- Spájaný zoznam
![[linked_list.excalidraw]]
- Pole
	- prvky sú uložené v susediacich bunkách poľa
	- jednoduchá implementácia
	- realizácia dynamického poľa
	- zvykne byť vo väčšine program. jazykoch
- Rozdiely:

Operácia|Pole|Spájaný
---|---|---
get|O(1)|O(n)
insert (všeob.)|O(n)|O(n)
insert (zač.)|O(n)|O(1)
insert (koniec)|O(1)|O(1)
delete (všeob.)|O(n)|O(n)
delete (zač.)|O(n)|O(1)
delete (koniec)|O(1)|O(1)