# Vstupno-výstupný podsystém

Charakteristika **vstupno-výstupného podsystému** je veľká rôznorodosť zariadení.

Problematika s veľkou rôznorodosťou je *všeobecná a štandardizovaná* implementácia pre tieto zariadenia.

Väčšina V/V zariadení je v [[Operačné systémy|OS]] reprezentovaná ako súbory.

## Prograové spracovanie komunikácie
Medzi zariadeniami sa komunikuje prostredníctov špecíalnych funkcií zvaných IN a OUT (podobne ako [[Práca so súbormi#read write fd|read a write]]).

## Spracovanie s prerušením
Procesor nečaká na pripravenosť [[Vstupno-výstupné zariadenia|zariadení]], ale zariadenie po ukončení prípravy vyvolá [[Prerušenia#Typy prerušení|prerušenie]].

Celkové fungovanie na 8086 mikroporcesore:
1. Zariadenie pošle žiadosť o prerušení
2. Procesor dokončí momentálny program a pošle potvrdenie zariadeniu
3. Procesor vykoná prerušenie
4. V/V posunie svoje inštrukcie procesoru (?)

## Ovládač zariadenia (device driver)
- softvér, ktorý ovláda zariadenie
![[device_driver.excalidraw]]
- niektoré zariadenia prichádzajú rovno s operačným systémom (buď ich už má v inštalačných súboroch, alebo si ich vie zabezpečiť nejakým spôsobom)

Spracovanie požiadaviek:
![[interrupt_driven_IO_cycle.excalidraw]]



---
- [[Vstupno-výstupné zariadenia]]
- [[Priamy prístup do pamäte]]
- [[Vstupno-výstupné rozhranie z pohľadu OS]]
- [[Plánovanie diskových operácií]]
- [[Implementácia súborového systému]]
---