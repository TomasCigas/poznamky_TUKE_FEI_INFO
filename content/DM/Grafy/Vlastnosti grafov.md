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
3. Prípadne môžeme prekresliť jeden z grafov tak, aby prekrýval ten druhý.
! Ak sú grafy izomorfné, tak ich vlastnosti sú totožné !
	
## Súvislosť

Graf  $G=(V,H)$ je **súvislý**, ak pre každú dvojicu vrcholov $u,v$ existuje medzi nimi [[Postupnosť vrcholov a hrán#Sled|sled]].

### Stupeň vrchola v grafe 
**Stupeň vrchola** je počet susedov vrchola.

_Def_.: Nech $G=(V,H)$ je graf a nech $u\epsilon V$.
Číslo $\delta _G(u)$ nazývame **stupeň vrchola** v grafe $G$, kde $\delta _G (u)$ = počet susedov vrchola / počet incidujúcich hrán.

_Veta_: Pre ľubovoľný graf $G=(V,H)$ platí: 
$$
\sum_{v\epsilon V} \delta_G(v) = 2*|H|
$$

_Def_.: Graf $G=(V,H)$, ktorý má $\forall$ vrcholy stupňa $k$ nazývame **pravidelný graf stupňa $k$**

$K_n$ je [[Grafy|pravidelný]] graf stupňa n-1

- pravidelný faktor grafu - [[Špeciálne typy grafov#Podgraf|podgraf]] obsahujúci vrcholy grafu a má rovnaké stupne vrcholov

### Grafová postupnosť
_Veta_: 
Počet vrcholov s nepárnym stupňom je v každom grafe číslo párne.
_D_: 
$$
\sum_{v\epsilon V} \delta_G(v) = \sum \square + \sum \bigstar = 2*|H|
$$
kde $\square$ je párne a $\bigstar$ je nepárne.
Súčet párnych čísel je párny, keďže aj výsledok je párny, musí byť súčet nepárnych čísel párnych.

Postupnosť čísel je **grafová**, ak existuje graf s odpovedajúcimi stupňami vrcholov.

_Veta_(Havlova):
Nech pre postupnosť $S_1,S_2,...,S_n$ celých nezáporných čísel platí:
$$
S_1\geq S_2\geq ...\geq S_n
$$
Tá postupnosť je **grafová** $\Leftrightarrow$ ak je grafová aj postupnosť  $S_2 - 1,S_3 - 1,...,S_{S+1}-1, S_{S+2},...,S_n$ 

## Komponent
**Komponent** grafu $G$ je každý jeho maximálny (obsahuje maximálny počet hrán a vrcholov) súvislý [[Špeciálne typy grafov#Podgraf|podgraf]].

_Veta_:
Nech $G=(V,H)$, $|V| = n$ je graf, v ktorom súčet stupňov ľubovoľnej dvojice nesusedných vrcholov je aspoň $n-1$. Potom graf $G$ je súvislý.
