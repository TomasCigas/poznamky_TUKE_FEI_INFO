# Prepínanie procesov
- je to proces výmeny  [[Procesy|procesov]] na procesore.

## Mechanizmy prepínania
Mechanizmus|Dôvod|Použitie
-----------|---------------|--------------------
Prerušenie|Extérna exekúcia momentálnej inštrukcie|Reakcia na asynchrónnu extérnu udalosťlosť  
Pasca|Asociované s internou exekúciou mom. inš.|Správa chyby alebo výnimki
Volanie nadriadeného|Explicitné požiadanie|Volanie na funkciu operačného systému

## Proces prepínania
1. Prepnutie režimu procesora
	- používatelský režim -> systémový režim
2. Zmena stavu procesora
	- uchovanie stavu procesora
	- aktualizácia momentálneho [[Procesy#Riadiaci blok procesu|PCB]] a jeho presunutie
	- **výber ďalšieho procesora**
	- aktualizácia nového PCB
	- obnovenie procesu
3. Prepnutie režimu procesora
	- systémový režim -> používatelský režim