# Úvod do medziprocesorovej komunikácie
Procesy v UNIXe sú samostatné entity nezávislé od seba, UNIX poskytuje však viacer metód komunikácie medzi nimi. Mechanizmus spracovania týchto medziprocesorových komunikácií sa nazýva **I**nter**P**rocess **C**omunication. Existujú následovné možnosti IPC:
- **signály** -> jedná sa o asynchrónne posielanie upozornení. Táto komunikácia neposiela žiadne dáta, ale informuje proces. Môžu ich posielať iné procesy alebo samotný operačný systém
- **rúry** -> najstarší komunikačný spôsob v UNIXe, tento už posiela aj dáta, majú svoje obmedzenia
- **pomenované rúry** -> dovoľujú komunikáciu s nepríbuzdnými procesmi.
- **Systém V IPC**-> obsahuje komunikačné mechanizmy:
	- _fronty správ_ -> zasielanie formátovaných postupností dát
	- _zdieľaná pamäť_ -> zdieľanie virtuálneho adresného priestora
	- _semafóry_ -> synchronizácia procesov
- **sockety** -> komunikácia nie len medzi procesmi, ale aj medzi počítačmi spôsobom klient-server

---
- [[Rúry]]
---