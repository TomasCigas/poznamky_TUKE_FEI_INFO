# Posielanie správ
Na [[Medziprocesorová komunikácia|kooperáciu]] procesov potrebujeme:
- [[Semafóry]]
- Komunikáciu

Všeobecný princíp posielania správ spočíva v 2 primitívach (základné operácie):
- **send(destination,massage)** -> [[#Posielanie|posielanie správy]]
- **recieve(source,message)** -> [[#Príjmanie|prijatie správy]]

**Kombinácie blokovaných/neblokovaných** používateľov:

Odosielateľ|Príjmateľ|Charakteristika
----|----|----
blokovaný|blokovaný|randezvous
neblokovaný|blokovaný|**najužitočnejší prípad**
neblokovaný|neblokovaný|nikto nečaká

**Vzťah odosielateľ/príjmateľ**:
- 1:1 -> privátna komunikácia
- 1:N -> "broadcast" (vysielanie)
- N:1 -> proces poskytuje služby ostatným
	- zvykne sa používať [[#Adresácia|schránka]] zvanej **port**
- M:N -> viac *server* procesov poskytuje služby viac klientom


---
- <**>
---