# Viacvláknovosť
Jednovláknový klasický prístup je vykonávanie inštrukcií za sebou.

**Viacvláknovosť** je schopnosť podporovať viacnásobné paralelné sekvencie vykonávania inštrukcií v rámci jedného procesu.

**Kategorizácia**:
![[multithread.excalidraw]]

**Amdalov zákon**:
![[amdal.excalidraw]]
- $f$ -> časť paralelizovatelného kódu
- aj mala časť seriového kódu má značný negatívny vplyv na zrýchlenie
**Riešenie dôsledkov**:
- Natívne viacvláknové aplikácie (malý počet procesov s veľkým počtom vláken)
- Multiprocesové aplikácie
- [[Objektovo orientované programovanie|Java]] aplikácie (JVM je viacvláknové)
- "Multiinštančné" aplikácie