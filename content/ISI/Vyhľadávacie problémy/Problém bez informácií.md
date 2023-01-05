**********************
Nemáme žiadne informácie o momentálnom stave priestoru

BFS > DFS - ak sa cieľ nachádza plytko v strome
DFS > BFS - vieme v akej hĺbke sa cieľ nachádza

# DFS
Vyhľadávanie do hĺbky. Strom najprv expanduje deti až potom uzly na rovnakej úrovni.

Vracia *prvé nájdenie riešenie*, ktoré *nemusí* byť *optimálne*.

**Časová zložitosť** - $O(b^m)$, kde:
- $b$ - branch faktor
- $m$ - maximálna hĺbka stromu
**Pamäťová zložitosť** - $O(b*m)$

# BFS
Vyhľadávanie do šírky. Strom najprv expanduje uzly na rovnakej úrovni a potom expanduje deti.

Vracia v prípade rovnocenných javov (teda hrán grafu/stromu) optimálne riešenie.

**Časová zložitosť** - $O(b^m)$, kde:
**Pamäťová zložitosť** - $O(b^m)$

# Iteratívne hĺbenie
Spojenie BFS a DFS: expandujeme do určitej hĺbky a potom ideme po úrovniach.

# Ostatné
- Obojstranné hľadanie - pošleme dvoch [[Vyhľadávacie problémy|agentov]] aby spolu hľadali riešenie.