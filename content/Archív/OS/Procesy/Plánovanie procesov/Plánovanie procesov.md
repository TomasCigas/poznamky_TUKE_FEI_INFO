# Plánovanie procesov (Scheduling)

**Plánovanie procesov** je v podstate je správa front.
Celkový diagram fungovania:
![[shceduling.excalidraw]]
- rozšírenie [[Stavy procesov#Trojstavový diagram|tohto]]
- *interaktívny používatelia* -> prechádza rovno z [[Typy plánovania#Dlhodobé|dlhodobého]] do [[Typy plánovania#Krátkodobé|krátkodobého]] plánovania

Znázornenie v stavovom diagrame:
![[scheduling_states.excalidraw]]

Cieľ plánovania je minimalizácia doby pobytu procesov vo frontoch, teda optimalizácia výkonnosti systému.

## Realizovanie plánovania
### Spôsob rozhodovania (Decision mode)
Determinuje čas, kedy sa vykonáva [[#Výberová funkcia|výberová funkcia]].

#### Nepreemptívny
Proces sa rozhdouje o opustení proceora:
- až po skončení programu
- najbližšia V/V operácia
- systémové volania
#### Preemptívny
Funguje na báze [[Prerušenia|prerušenia]].

### Výberová funkcia
Určuje ktorý proces sa bude vykonávať ako nasledujúci.
Môže mať rôzne [[Typy plánovania#Kritéria správania|parametre]].


---
- [[Typy plánovania]]
- [[Algoritmy plánovania]]
---