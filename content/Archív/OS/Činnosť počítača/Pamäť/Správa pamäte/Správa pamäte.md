# Správa pamäte
Závisí v dynamickom prideľovaní fyzickej pamäte operačným systémom jednotlivým paralelne vykonávajúcim sa aplikáciám.

Jej hlavnou úlohou je umiestniť proces do hlavnej pamäte aby mohol byť vykonaný procesorom.

Pokiaľ sa nachádza v pamäti **málo aplikácií** dochádza k dlhšiemu blokovaniu aplikácií čakaním na vstup alebo výstup -> procesor nie je vyťažený. Teda snažíme sa maximalizovať počet aplikácií v operačnej pamäti.

## Priemiestňovanie programu
(Relokácia)
- postupom času sa presúva program z jednej oblasti do inej
![[relocation.excalidraw]]


## Ochrana programu
- ide o tvorbu bariér, ktoré bránia ostatným programom vniknúť do vnútra programu a ovplyvňovať jeho dáta
- napr. po alokovaní pamäte programu, nie je schopný tento program zasahovať mimo toto vymedzenie
![[prot.excalidraw]]

## Zdieľanie častí
- ide o zdieľanie niektorej časti medzi programami
- napr. dáta dokážeme zdieľať pomocou [[IPC|IPC]] a kód spoločnými knižnicami, alebo spustením jedného programu viackrát s inou verziou dát
![[sharing.excalidraw]]

## Logicá organizácia
- ide o abstraktný a zložitý spôsob ukladania dát, napr. rôzne typy premenných (čísla, znaky), štruktúry a pod.

## Fyzická organizácia
- ide o fyzické uloženie dát, jednoducho za sebou

## Hardvérový mechanizmus
![[hw_supp_mem.excalidraw]]
- tento mechanizmus slúži na ochranu ostatných procesov pred zasahovaním a taktiež aj na jednoduchú [[#Priemiestňovanie programu|relokáciu]]


---
- [[Pojmy pamäť]]
- [[Historické prístupy]]
---