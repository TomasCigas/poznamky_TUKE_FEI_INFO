***********
**Cloud computing** vykonávaný v cloudových systémoch je výpočtový proces, ktorý sa nevykonáva na zariadení, z ktorého pochádza požiadavky na daný výpočet.

**Cloud** je teda základom moderného počítania a obsahuje nasledovné princípy:
- *Fyzické* - škálovateľný masívny komplex globálne prepojených počítačov
- *Logické* - kolekcia jednoducho škálovateľných nástrojov, ktoré umožňujú vytvárať a rozširovať vývojárom ich projekty
- *Konceptuálne* - zbierka myšlienok škálovateľnosti vo veľkých systémoch #add_info 

# Vrstvenie
V dnešných cloduových systémoch predpokladáme, že máme veľké množstvo zákazníkov, preto chceme čo najviac odľahčiť klienta.

Z toho dôvodu rozdeľujeme náš systém na vrstvy:
1. Tier 1 - program, ktorý generuje web, teda vrstva, ktorá je najbližšie pri používateľovi
	- nepoužívajú veľa zdrojov
	- nepoužívajú I/O siete často
1. Tier 2  - služby, ktoré podporujú a dodávajú informácie prvej vrstve
	- môžu tu byť mikroslužby a databázy
	- táto vrstva sa ďalej rozdeľuje podľa potrieb aplikácie


# Mikroslužby
Mikroslužba je veľmi malá a jednoduchá aplikácia, obvykle single-threaded. Moderné cloudové systémy poskytujú možnosť **elasticity** týchto mikroslužieb, čo znamená automatické zmenšovanie alebo zvyšovanie množstva inštancií, podľa záťaže.

---
- [[História]]
- [[IoT a cloudy]]
---