# Prerušenia
**Prerušenie** je mechanizmus, ktorý umožňuje narušiť [[Činnosť počítača#Sekvenčné vykonávanie programu|sekvenčné spracovanie]]. Je to principiálny mechanizmus fungovania OS.

 Zvyšuje efektivitu niektorých činností a otvára nové možnosti, ktoré by sme bez prerušení neboli schopný urobiť. 
 
 ## Typy prerušení
- Vonkajšie -> od [[Vstupno výstupné zariadenia|V/V zariadení]]
- Vnútorné:
	- Programové -> inštrukcia INT (volanie služieb [[Operačné systémy#BIOS|BIOSu]], OS)
	- Od procesora -> reakcie na udalosti
		- časovač
		- chyby
		- ...

- Jednoduché
- Viacnásobné
	- môže spôsobovať problémy

## [[Vykonávanie inštrukcií#Inštrukčný cyklus|Inštrukčný cyklus]] a prerušenia
![[interrupt_cycle.excalidraw]]
