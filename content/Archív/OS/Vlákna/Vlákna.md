# Vlákna
**Vlákno** je jednotka (objekt) [[Vykonávanie inštrukcií|vykonávania inštrukcií]].
 
 **Vlákno** je sekvenčná postupnosť inštrukcií v rámci riadenia programu.
 
 Vlakno je charakterizované:
 - stavom vykonávania
 - uchovaným konextom
 - zásobníkom
 - statickým úložiskom dát
 - zdieľanie zdrojov s ostatnými vláknami v rámci procesu

Viacvláknový model výpočtov z pohľadu procesu
![[multithread_process.excalidraw]]
- [[Procesy#Riadiaci blok procesu|PCB]]
- [[#Typy vláken|haldy]]

**Výhody**:
- *vytvorenie, ukončenie a prepínanie* v rámci vlákien je omnoho jednoduchšie a zaberá menej času ako robiť tieto činnosti s procesmi -> zníženie režijného času OS
- efektívnejša komunikácia (nepotrebujeme [[Medziprocesorová komunikácia|IPC]])
- proces sa vďaka viacerým vláknam môže vykonávať na viacerých [[Procesor|procesoroch]]

Vlákna môžu byť navzájom nezávislé, ale aj závislé -> v tomto prípade je potrebná synchronizácia, podobne ako pri [[Synchronizácia|procesoch]]

Stavový diagram vlákna:
![[thread_states.excalidraw]]

## Typy vláken
### Používatelské
Riadenie vláken prostredníctvom aplikácie, pri čom jadro neeviduje ich existenciu.
Každý [[Procesy|proces]] začína práve jedným vláknom.
![[threds_user.excalidraw]]

**Výhody**:
- väčšia kontrola nad vláknami
- jadro sa nemusí starať o prepnutie vláken
**Nevýhody**:
- [[Operačné systémy|operačný systém]] nevie o viacerých vláknach -> pri zablokovaní jedného z vláken sa môže zablokovať celý proces
- keďže sa pre operačný systém berie proces s vláknami ako jeden celok, nemôžeme využívať [[Klasifikácie#Počtu paralelne bežiacich úloh|multiprogramovanie]]

### Systémové (Kernel)
Celé riadenie vláken sa uskutočňuje na úrovni jadra.
Jadro uchováva kontext nie len procesov ale aj jednotlivých vláken.

![[threads_kernel.excalidraw]]
**Výhody**:
- paralélny beh jednotlivých vláken

**Nevýhody**:
- manipulácia s vláknami je o mnoho drahšia ako pri [[#Používatelské|používatelských]], ale stále lepšia ako pri [[Procesy|procesoch]] 

### Kombinované
![[threads_combined.excalidraw]]
Kombinácia [[#Používatelské|používatelského]] a [[#Systémové Kernel|systémového]] používania vláken.

---
- [[Viacvláknovosť]]
---