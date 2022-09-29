# Rúry
## pipe(rúra)
Umožňuje komunikáciu medzi príbuznými procesmi. Fungujú na základe zapísania dát na jednom konci rúry a prečítania na tom druhom.

Rúra je závislá od dedičstva, takže tento mechanizmus sa nedá exportovať zo stromu potomkov.

Rúry sú somosynchronizačné, ale len na úrovni jedného volania jadra na čítanie, pri zvýšení počtu procesov, ktoré z rúry čítajú, môže dojsť ku konfliktom medzi procesmi.

### Syntax
```c
#include <unistd.h>
int pipe(int file[2])
```
### pipe()
- argument  `file[2]` slúži na uloženie deskriptora pre rúru ktorá je vytvorená týmto príkazom
- `file [0]` slúži na čítanie
- `file [1]` slúži na zápis
- na zápis a čítanie z/do rúry sa používa [[Práca so súbormi#read write fd|read a write]]

- keďže musia byť procesy na ktorých používame rúry príbuzné, musíme použiť príkazy ako `fork()` alebo `exec()` na spustenie druhého procesu

## fifo(pomenovaná rúra)
