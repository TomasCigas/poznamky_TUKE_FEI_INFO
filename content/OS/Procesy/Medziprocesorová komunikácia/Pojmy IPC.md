# Pojmy IPC

## Atomická operácia
- činnosť ktorá sa vykoná **celá**, alebo **vôbec**
- napr.: inštrukcie procesora

## Kritická sekcia
- časť **programu**, ktorá pracuje s *krtickým (zdieľaným) zdrojom*

## Deadlock (uviaznutie)
- systém sa dostane do stavu, v ktorom ani jeden proces nepokračuje vo svojej činnosti
- nastáva, keď všetky procesy čakajú na ostatné

## Livelock (živé uviaznutie)
- systém sa dostáva do stavu, v ktorom každý proces mení svoj stav, bez toho aby robil užitočnú prácu

## Vzájomné vylúčenie (Mutual exclusion)
- pokiaľ sa jeden [[Procesy|proces]] nachádza v istej [[#Kritická sekcia|kritickej sekcii]], žiadny iný proces nemôže manipulovať s touto kritickou sekciou.

## Podmienka závodov (Race condition)
- situácia, v ktorej viacero *vlákien* alebo [[Procesy|procesov]] zapisuje či číta z [[#Kritická sekcia|kritického zdroja]] a finálny výsledok závisí od ich relatívneho času spustenia a vykonania

#add_link

## Vyhladovanie
- situácia, v ktorej bol procesu odmietnutý prístup k vyžadovaným zdrojom, obvykle pretože s týmto zdrojom narába iný proces
