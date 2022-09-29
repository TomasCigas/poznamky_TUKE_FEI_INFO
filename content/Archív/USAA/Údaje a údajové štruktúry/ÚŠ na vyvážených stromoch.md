# ÚŠ na vyvážených stromoch

## Zľučovateľná halda
[[Údaje a údajové štruktúry|ÚŠ]] určené na vykonávanie inštrukcií $INSERT$, $DELETE$, $UNION$/$MERGE$, $MIN$ v čase $O(log(n))$

Ide o zovšeobecnenie štruktúry **halda**.

Využitie [[Reprezentácia stromov#2-3 stromy|2-3 stromov]] pre zľučovateľné haldy:
- $\forall$ prvok $S$ je značkou listu $T$, listy nie sú lineárne usporiadané
- $\forall$ každý nelistový vrchol v $T$ je oznaćený značkou $SMALLEST[v]$ -> najmenší prvok v podstrome s koreňom $T$
- označenia $L[v]:M[v]$ nie sú potrebné

### Operácie
**MIN**:
- začíname v koreni $T$ a postupujeme k listom:
	- z nelistového vrcholu $v$ ďalej navštívime syna $v$ s najnižšou hodnotou $SMALLEST$
	- ak má $T$ $n$ listov, potrebujeme maximálne $O(log(n))$ krokov
- zvyčajne odstraňujeme najmenší prvok

**UNION**:
- predpoklad -> $\forall$ množina reprezentovaná [[Reprezentácia stromov#2-3 stromy|2-3 stromom]]
- na zlúčenie $S_1,S_2$ s koreňmi $T_1,T_2$ používame $IMPLANT$
	- predpokladáme, že výška $T_1$ je menšia ako $T_2$
	- nájdeme vrchol $v$ v $T_1$ s výškou $T_2$ 
	- aktualizujeme $SMALLEST$
	- čas zjednotenia -> $O(h_1 - h_2)$

- rozlišovanie "ľavého" a "pravého" nie je podstatné, zavádzame pre [[#Spájateľný front|spájateľné fronty]]
- Ak uvažujeme aktualizáciu L a M, $IMPLANT$ potrebuje $O(max(log|S_1|,log|S_2|))$ operácií

## Spájateľný front
Predpokládame značenie [[Reprezentácia stromov#2-3 stromy|2-3 stromov]], kde listy s prvkami $S$ zľava doprava vo vzrastajúcom poradí.

### Operácie
**CONCATENATE$(S_1,S_2)$**:
- zreťazenie postupností

**SPLIT**:
- rozdelenie  $S$ na dve časti podľa prvku $a$

**DIVIDE**:
- vytvorí [[Reprezentácia stromov#2-3 stromy|2-3 stromy]] $T_1,T_2$ s prvkami $S_1,S_2$
- neformálne:
	- nech $T$ obsahuje $a$, nájdeme cestu z $r$ do listu $l$
	- cesta vytvorí 2 množiny podstromov, korene ktorých sú synmi vrcholov na tejto ceste
	- stromy naľavo -> $S_1={b|b\leq a,b \in S}$
	- stromy napravo ->$S_2={b|b > a,b \in S}$
- rozdelí 2-3 strom $T$ vzhľadom na list $a$, pri čom sa poradie nemení
- zložitosť: $O(max(log|S_1|,log|S_2|))$ 