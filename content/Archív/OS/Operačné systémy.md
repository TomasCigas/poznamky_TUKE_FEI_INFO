# Operačné systémy
**Operačný systém** je program, ktorý *riadi vykonávanie aplikačných* programov a zároveň sa správa ako *interfejs medzi aplikáciami a počítačoým hardvérom*, teda funguje ako *sprostredkovateľ medzi používateľom a hardvérom* počítača.
Úlohou operačných systémov je poskytnutie prostriedia pre používateľa, aby mohol vykonávať programy efektívne.

Hardvér musí poskytovať dostatočné zabezpečenie, aby používateľ neovplyvnil ich korektné fungovanie, alebo ich akýmsi spôsobom zneužiť.

Nekonvenčný hardvér taktiež zvykne poskytovať svoj vlastný softvér (tzv. driver), aby ho mohol operačný systém správne použiť.

OS ako riadiaci program zabraňuje vzniku chýb a nekorektnému použitiu počítača.

Špecíalnu pozornosť venuje činnosti a riadeniu [[Vstupno-výstupné zariadenia|V/V zariadení]].

## BIOS
**BIOS** alebo ***B**asic **I**nput **O**utput **S**ystem* je základný program PC ktorý slúži ako sprostredkovateľ medzi hardvérom a (zvyčajne) operačným systémom. Obvykle je "vypálený" na read-only pamäť základnej dosky a je to prvý program, ktorý sa po zapnutí počítača spustí

## Kernel
Kernel je základná časť operačného systému, ktorá poskytuje služby ostatným častiam OS.

Je to hlavná vrstvá medzi OS a hardvérom.

Lepšia vizualizáciu je [[Štruktúra operačných systémov#UNIX|tu]].

## Správa zdrojov
Každá časť operačného systému spravuje neaký zdroj, napr.:
- čas procesora -> spravuje synchronizáciu
- aresný priestor -> spravuje pamäť
- diskový priestor -> spravuje ukladaciu pamäť
- V/V zariadenia -> spavuje periférne zariadenia
- ...

---
- [[Zadanie]]
- [[História operačných systémov]]
- [[Štruktúra operačných systémov]]
- [[Klasifikácie]]
- [[Bezpečnosť]]
- [[Činnosť počítača]]
- [[Procesy]]
- [[Pamäť]]
- [[Vlákna]]
- [[Vstupno-výstupný podsystém]]
---
