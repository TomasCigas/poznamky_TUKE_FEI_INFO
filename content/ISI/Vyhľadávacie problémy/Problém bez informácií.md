**********************
Nemáme žiadne informácie o momentálnom stave priestoru

BFS > DFS - ak sa cieľ nachádza plytko v strome
DFS > BFS - vieme v akej hĺbke sa cieľ nachádza

# DFS
Vyhľadávanie do hĺbky. Strom najprv expanduje deti až potom uzly na rovnakej úrovni.

Vracia *prvé nájdenie riešenie*, ktoré *nemusí* byť *optimálne*.

**Časová zložitosť** - $O(b^m)$, kde:
- $b$ - branch faktor
- $m$ - maximálna hĺbka stromu (hĺbka k cieľu)
**Pamäťová zložitosť** - $O(b*m)$

# BFS
Vyhľadávanie do šírky. Strom najprv expanduje uzly na rovnakej úrovni a potom expanduje deti.

Vracia v prípade rovnocenných javov (teda hrán grafu/stromu) optimálne riešenie.

**Časová zložitosť** - $O(b^m)$
**Pamäťová zložitosť** - $O(m)$

# Iteratívne hĺbenie
Spojenie BFS a DFS: expandujeme ako DFS, ale len do určitej hĺbky, a potom prechádzame na ďalšieho potomka (ako BFS)

Nachádza *optimálne* riešenie.

**Časová zložitosť** - $O(b^m)$
**Pamäťová zložitosť** - $O(b*m)$
?

# Ostatné
- Obojstranné hľadanie - pošleme dvoch [[Vyhľadávacie problémy|agentov]] aby spolu hľadali riešenie.