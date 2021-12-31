# Spúštanie procesov

Má 4 štádiá:
## Vytvorenie procesu

Počas svojej existencie je schopný proces aj vytvárať ďalšie procesy, tzv. fork.
Pri takejto tvorbe sa medzi týmto a novým procesom vytvára vzťah **rodič-potomok**.
Tieto procesy môžu zdieľať _všetky, niektoré alebo žiadne_ prostriedky.
Rodič môže buď čakať kým sa potomok ukončí, alebo beží paralélne.

Komunikácia medzi procesmi je možná pomocou [[IPC|IPC]] alebo stavov.

## Naplánovanie na vykonávanie
Slúži na rozhodovanie o tom, kedy a čo sa s [[Procesy|procesmi]] deje.
Má za úlohu migrácie procesov medzi frontmi.

Operačný systém o tomto rozhoduje pomocou **plánovača**.

### Dlhodobý plánovač
(Plánovač prác)
- Rozdhoduje o zaradení do frontov
### Krátkodobý plánovač
(Plánovač procesora)
- Rozhdouje o zaradení do procesora
### Strednodobý plánovač
(Taktický plánovač)
- Rozhoduje o zaradení medzi odsunutými a pripravenými procesmi

## Spustenie nášho programu

## Vykonanie programu
Po jeho [[#Spustenie nášho programu|spustení]] sa vykonáva [[Vykonávanie inštrukcií#Inštrukčný cyklus|inštrukčný cyklus]].
Vykonávanie má teda:
- svoje inštrukci
- stav a pamäť
- priestor, kde môže inštrukcie vykonávať (zdroje)
- vzťahy s okolitým svetom (komunikácia s inými procesmi)

## Ukončenie procesu
Všetky zdroje priradené tomuto procesu sú uvoľnené:
- Fyzická a virtuálna pamäť
- Otvorené súbory
- Vyrovnávacie pamäte