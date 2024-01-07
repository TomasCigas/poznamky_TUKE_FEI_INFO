***********
Popisuje priebeh programu detailne po krokoch. Prechod vyzerá následovne:
$$
\langle S,s\rangle \Rightarrow \alpha
$$
kde $\alpha$ môže byť:
- stav $s'$ - koncový ak sa *vykoná príkaz v jednom kroku*
- konfigurácia $\langle S,s'\rangle$ - ďalšia konfigurácia, kde sme zredukovali $S \rightarrow S'$, príkaz sa teda *nevykoná v jednom kroku*


Odvodzovacie pravidlá sú obdobné ako pri [[Prirodzená sémantika|prirodzenej sémantike]], príkaz cyklu je avšak iný:
$$
\langle while\ b\ do\ S,s\rangle \Rightarrow \langle if\ b\ then\ (S;while\ b\ do\ S)else\ skip\ ,s\rangle
$$

Zápisy: 
- $\alpha_i \Rightarrow \alpha_{i+1}$ - vykonanie jedného kroku
- $\alpha \Rightarrow^k \alpha'$ - vykonanie $k$ krokov
- $\alpha \Rightarrow^* \alpha'$ - vykonanie konečného počtu krokov
- $\alpha \Rightarrow ...$ - vykonanie nekonečného počtu krokov

Štrukturálna operačná sémantika sa používa na konkrétnu implementáciu jazyka.
Na tieto účely sa teda používa **abstraktná implementácia jazyka** vo forme:
- definícia [[Abstraktný stroj|abstraktného stroja]](AS)
- **preklad** programu do inštrukcií AS
- **vykonanie** AS

---
