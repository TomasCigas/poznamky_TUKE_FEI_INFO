# Zdieľanie času a zdrojov
Prvé počítače vykonávali len jeden program a až po jeho skončení sa mohol vykonávať ďalší. Bolo to neefektívne a v mnohých prípadoch nepraktické, preto sa začal používať tzv. multiprogramming, teda začal sa zdieľať čas medzi procesmi

## Technická realizácia multiprogramovania
- ide len o ilúziu paralelnosti, keďže nedokážeme zabezpečiť vykonávanie viacerých programov na jednom procesore

Realizácia je pomerne jednoduchá, len odkladáme aktuálny program a obnovujeme nejaký iný, musíme však byť schopný uložiť momentálny stav nášho odloženého programu.
![[exchange.excalidraw]]

Odoženie programu v podstate znamená odstavenie jeho prístupu do procesora. Potrebujeme teda vykonať nejaký proces, ktorý zabezpečí výmenu programov na procesore.

Na samotnú výmenu programov máme dva mechanizmy:
- **Kooperatívny multitasking** -> program sa svojvoľne vzdá svojmu prístupu _(zastaraný)_
![[exchange_sub.excalidraw]]
- **Preemptívny multitasking** -> zásah zvonku, teda program bude násilne odstavený od procesora napr. [[Operačné systémy|operačným systémom]]
![[exchange_dom.excalidraw]]

Samozrejme potrebujeme miesto, kam sa budú všetky informácie, ktoré chceme z procesora uvolniť, táto štruktúra sa nazýva **[[Procesy#Riadiaci blok procesu|riadiaci blok]]**. Do tohto riadiaceho bloku teda odkladáme hlavne registre rôznych druhov (potrebné na program, ochrana a i.). Teda:

Najprv sa uložia potrebné dáta do riadiaceho bloku PCB1.
![[exchange_save.excalidraw]]

A potom sa načítajú z bloku PCB2 aby sa potom mohol ďalej vykonávať program P2.
![[exchange_load.excalidraw]]

Náš program výmeny si musí udržiavať nejakú evidenicu o našich odložených programoch, aby nedošlo k pomiešaniu dát.

Proces prepnutia je _čistou stratou_, teda nevykonáva sa žiadna užitočná práca CPU. Operácia striedaná je _drahá_, pretože trvá pomerne dlho.