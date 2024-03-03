***********
Operačná sémantika sa sústreďuje na formálny popis vykonávania programu. Teda ak popíšeme príkazy programu ako $S$ a [[Sémantika#Stav|stav]] pamäte ako $s$, tak vykonanie popisujeme ako:
$$
\langle S,s \rangle
$$
Ako prechod medzi jednotlivými stavmi a príkazmi (teda redukcia) používame buď:
- $\langle S,s \rangle \rightarrow \langle S,s' \rangle$ pre [[Prirodzená sémantika|prirodzenú sémantiku]]
- $\langle S,s \rangle \Rightarrow \langle S,s' \rangle$ pre [[Štrukturálna operačná sémantika|štrukturálnu operačnú sémantiku]]

Definícia operačnej sémantiky nevyužíva sémantické rovnosti, ale **axiómy** a **odvodzovacie pravidlá**.
Všeobecný zápis pravidla pre odvodenie je:
![[odvodzovacie_pravidlo.excalidraw]]

kde:
- nad čiarou sa nachádzajú *predpoklady* pravidla
- pod čiarou sa nachádza *záver* pravidla
- *podmienka* nemusí byť v každom pravidle a musí platiť pred použitím daného pravidla

**Axióma** je teda odvodzovacie pravidlo, ktoré nemá ani predpoklady ani podmienky.
**Jednoduché odvodzovacie pravidlo** nemá podmienku.