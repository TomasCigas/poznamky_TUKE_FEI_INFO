# Vlastnosti grafov
Nech $G_1=(V_1,H_1)$ a $G_2=(V_2,H_2)$ sú [[Grafy|grafy]].

## Komplementárnosť
**Komplementom** grafu $G=(V,H)$ nazývame graf $\neg G = (V,{V\choose 2}/H)$. 
	- Teda grafý $G$ a $\neg G$ sú komplementárne
	- $G\cup \neg G = K_n\ ,|V|=n$
	- $G\cap \neg G = D_n$ -> **diskrétny** graf na n vrcholoch (neobsahuje hrany)
![[graf4.png]]

## Izomorfizmus
Hovoríme, že grafy $G_1$ a $G_2$ sú izomorfné ($G_1 \cong G_2$), ak existuje [[Zobrazenia#Druhy zobrazení|bijektívne zobrazenie]] z množiny $\phi :V_1$ -> $V_2$, také že platí : 
$$
\forall u,v \epsilon V_1 : \{u,v\} \epsilon H_1 \Leftrightarrow \{\phi (u),\phi (v)\} \epsilon H_2
$$
- taktiež nazývané ako [[Grafy|zachovanie incidencie]].

Postup nájdenia:
1. $G_1$ a  $G_2$ majú rovnaký počet hrán a vrcholov.
2. Hľadáme také bijektívne zobrazenie, ktoré spĺňa zachovanie incidencie.
	- pri nesplnení upravujeme graf, tak aby predošlá podmienka spĺňala.
	- dúfame, že spĺňa inak je bijektívnych zobrazení n!
 
 - Spôsoby nájdenia:
 1. Grafy majú rovnaký počet vrcholov
 2. Graf sa dá prekresliť tak, aby vyzeral totožne

 - Spôsoby vyvrátenia:
 4. Nájdenie kružnice, ktorá sa v druhom nenachádza
 5. Rozdielny maximálny stupeň grafu
 6. Rozdielny stupeň susedov vo vrchole s maximálnym stupňom

! Ak sú grafy izomorfné, tak ich vlastnosti sú totožné !

! Ak sú grafy komplementárne, nie sú izomorfné ! - dokázať

! Grafy sú izomorfné ak jedna z permutácií stĺpcov a riadkov ich [[Vzdialenosti v grafe#Matica incidencie|matíc incidencie]] je rovnaká.
	
## Súvislosť

Graf  $G=(V,H)$ je **súvislý**, ak medzi každou dvojicou vrcholov $u,v$ existuje [[Postupnosť vrcholov a hrán#Cesta|cesta]]. Súvislý graf musí mať jeden [[#Komponent|komponent]].

### Faktor grafu
- [[Špeciálne typy grafov#Podgraf|podgraf]] [[Grafy|grafu]] $G$ ktorý obsahuje všetky vrcholy grafu $G$
- **k-faktor** grafu je faktor, ktorého každý vrchol má $k$ stupeň

### Stupeň vrchola v grafe 
**Stupeň vrchola** je počet susedov vrchola.

_Def_.: Nech $G=(V,H)$ je graf a nech $u\epsilon V$.
Číslo $\delta _G(u)$ nazývame **stupeň vrchola** v grafe $G$, kde $\delta _G (u)$ = počet susedov vrchola (resp. počet incidujúcich hrán).

_Veta_: Pre ľubovoľný graf $G=(V,H)$ platí: 
$$
\sum_{v\epsilon V} \delta_G(v) = 2*|H|
$$

_Def_.: Graf $G=(V,H)$, ktorý má $\forall$ vrcholy stupňa $k$ nazývame **pravidelný graf stupňa $k$**

$K_n$ je [[Špeciálne typy grafov|pravidelný]] graf stupňa n-1

- pravidelný [[Vlastnosti grafov#Faktor grafu|faktor grafu]] - faktor grafu, ktorého stupne vrcholov sú všetky rovnaké

- vrchol s **maximálnym** stupňom musí byť menší ako počet vrcholov s nenulovým stupňom v grafe

### Grafová postupnosť
Postupnosť čísel je **grafová**, ak existuje graf s odpovedajúcimi stupňami vrcholov.

_Veta_(Havlova):
Nech pre postupnosť $S_1,S_2,...,S_n$ celých nezáporných čísel platí:
$$
S_1\geq S_2\geq ...\geq S_n
$$
Tá postupnosť je **grafová** $\Leftrightarrow$ ak je grafová aj postupnosť  $S_2 - 1,S_3 - 1,...,S_{S+1}-1, S_{S+2},...,S_n$ 

_Veta_: 
Počet vrcholov s nepárnym stupňom je v každom grafe číslo párne.
_D_: 
$$
\sum_{v\epsilon V} \delta_G(v) = \sum \square + \sum \bigstar = 2*|H|
$$
kde $\square$ je párne a $\bigstar$ je nepárne.
Súčet párnych čísel je párny, keďže aj výsledok je párny, musí byť súčet nepárnych čísel tiež párnych.

## Komponent
**Komponent** grafu $G$ je každý jeho maximálny (obsahuje maximálny počet hrán a vrcholov) súvislý [[Špeciálne typy grafov#Podgraf|podgraf]].

_Veta_:
Nech $G=(V,H)$, $|V| = n$ je graf, v ktorom súčet stupňov ľubovoľnej dvojice nesusedných vrcholov je aspoň $n-1$. Potom graf $G$ je súvislý.

## Kostra
**Kostra** grafu je taký [[#Faktor grafu|faktor grafu]], ktorý je [[Špeciálne typy grafov#Strom|stromom]].
Počet kostier grafu môžeme získať výpočtom determinantu matice $det(D-B)$, kde $D$ je [[Vzdialenosti v grafe#Diagonálna matica|diagonálna matica]] a $B$ je [[Vzdialenosti v grafe#Matica susednosti|matica susednosti]], pri čom z výslednej matice vyradíme ľubovoľný riadok a stĺpec $i$ (musia mať rovnaký index).

## Homeomorfizmus
- dva grafy sú izomorfné, pokiaľ sú [[#Izomorfizmus|izomorfné]] alebo vznikli **rozpoľtením hrán** (na hranu sa pridá vrchol so stupňom 2)

## Planárnosť
- graf je **planárny** pokiaľ sa jeho hrany nepretínajú, resp. sa dá prekresliť do roviny tak, aby sa nepretínali
- **eulerova formula** udáva, že pokiaľ máme súvislý, planárny graf _(zakreslený tak, že sa nepretínajú hrany)_, počet stien $r$ v tomto grafe sa dá vypočítať ako:
$$
|H| - |V| + 2 = r
$$
- pomocou eulerovej formuly teda vieme vydedukovať, že pokiaľ je graf planárny tak každá stena (okrem vonkajšej) je ohraničená aspoň 3 vrcholmi a každá hrana sa dotýka maximálne dvoch stien, matematicky povedané, že ak gra nespĺňa:
$$
|H| \leq 3*|V|-6
$$
tak určite **nie je** planárny

- pokiaľ však spĺňa túto podmienku, stále nemusí byť planárny, v tomto prípade hľadáme či graf nemá podgrafy homeomorfné s [[Špeciálne typy grafov#Kompletný graf|grafmi]] $K_5$ alebo $K_{3,3}$, keďže tieto sú najmenšie neplanáre grafy (Kuratowského veta)

- pokiaľ je graf [[Špeciálne typy grafov#Strom|stromom]] tak je planárny

Postup pre zisťovanie planárnosti grafu(?):
1. $|H| \leq 3*|V|-6$
2. Pokiaľ graf nemá [[Postupnosť vrcholov a hrán#Kružnica|kružnicu]] dĺžky 3, tak $|H| \leq 2*|V| -4$
3. $r \leq 2 *|V| - 4$

## Eulerovskosť
- graf je **eulerovský** pokiaľ sa v ňom nachádza tzv. **eulerovský ťah** -> [[Postupnosť vrcholov a hrán#Ťah|ťah]], ktorý prechádza každou hranou

- pokiaľ všetky vrcholy v grafe majú párny stupeň, tak existuje eulerovský ťah
- pokiaľ má graf práve 2 vrcholy nepárneho stupňa, existuje eulerovský ťah

## Hamiltonovskosť
- graf je **hamiltonovský** pokiaľ sa v ňom nachádza tzv. **hamiltonovská kružnica** -> [[Postupnosť vrcholov a hrán#Cesta|cesta]], ktorá prechádza každým vrcholom

Vety:
- pokiaľ graf obashuje **most** alebo **artikuláciu** nemôže byť hamiltonovský
	- **most** -> hrana, ktorú po vynechaní z grafu sa v ňom zvýši počet komponentov
	- **artikulácia** -> vrchol, ktorý po vynechaní z grafu sa v ňom zvýši počet komponentov
- pokiaľ je graf diparcitný s rovnakým počtom vrcholov v partíciách, tak je aj hamiltonovský
- pokiaľ graf $G = (V,H)$, kde $|V| \geq 3$  a každý vrchol $v\epsilon V$ spĺňa:
$$
\delta _v \geq \frac{|V|}{2}
$$
tak je graf hamiltonovský
- pokiaľ pre ľubovoľné dva vrcholy $v$ a $u$ grafu $G = (V,H)$, kde $|V| \geq 3$ platí:
$$
\delta _v + \delta _u \geq |V|
$$
tak je graf hamiltonovský