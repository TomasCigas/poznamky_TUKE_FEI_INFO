# Semafóry
**Semafór** je nezáporná hodnota, ktorá slúži na synchronizáciu [[Procesy|procesov]].

Nad semafórmi robíme 3 operácie:
- Inicializácia
- Inkrementácia (V)
- Dekrementácia (P)

Dekrementácia môže spôsobiť blokovanie procesu a inkrementácia zasa jeho odblokovanie. (Ak dekrementujeme pod 0)

## Binárny semafór
- semafór len s dvoma hodnotami (0,1)

## Mutex
- podobne ako [[#Binárny semafór|binárny semafór]] môže nadobúdať len 2 hodnoty
- rozdiel je, že iba ten [[Procesy|proces]], ktorý ho zablokuje, ho musí aj odblokovať

## Podmienená premenná (Conditional Variable)
- typ premennej, ktorá sa používa na zablokovanie [[Procesy|procesu]] alebo _vlákna_ dokým sa nesplní istá podmienka

## Nedostatky
- Neexistuje spôsob ako sa dozvedieť či bude proces zablokovaný
- Nevieme zistiť koľko procesov čaká na semafor
- Na jednoprocesorovom systéme nevieme zistiť ktorý z procesov bude bežať ihneď po inkrementovaní semafóru
