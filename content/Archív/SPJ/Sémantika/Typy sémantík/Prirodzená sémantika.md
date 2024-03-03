***********
Prirodzená sémantika formálne popisuje vzťah medzi počiatočným vzťahom, v ktorom sa vykonáva príkaz a koncový stav po jeho vykonaní.
Zaoberá sa len zmenou stavu celého príkazu.

[[Operačná sémantika|Odvodzovacie pravidlo]] prirodzenej sémantiky je podobné ako pri operačnej:
![[prirodzena_pravidlo.excalidraw]]
kde:
- príkazy $S_1$ až $S_n$ sú komponenty príkazu $S$
- $s_0$ je počiatočný stav
- $s_n$ je konečný stav
- $s_{0 \rightarrow n}$ sú medzistavy

Tento formálny zápis čítame ako:
"*Ak* vykonanie príkazu $S_1$ v stave $s_0$ zapríčinilo zmenu stavu na $s_1$ ... až kým vykonanie príkazu $S_1$ v stave $s_{n-1}$ zapríčinil zmenu stavu na $s_n$ , *potom* vykonanie celého príkazu $S$ v počiatočnom stave zapríčinilo zmenu stavu na koncový stav $s_n$"

Takýmto rozkladaním jednotlivých príkazov na podpríkazy (ich vykonanie na istých stavoch a medzistavoch) dostávame tzv. **odvzodzovací strom**, v ktorom:
- koreň stromu tvorí prechod programu (teda obsahuje celý príkaz programu)
- každý vrchol vzniká aplikáciou odvodzovacieho pravidla na predošlí vrchol (začíname teda koreňom)
- každý list je axíoma

**Vlastnosti prirodzenej sémantiky:**
- Príkaz $S$: 
	- v stave $s$ terminuje, ak existuje stav $s'$, taký, že: $$\langle S,s \rangle \rightarrow s'$$
	- **vždy** terminuje, ak terminuje v ľubovoľnom stave
	- pokiaľ neexistuje stav $s'$, tak program neterminuje
	- teda **nikdy** neterminuje ak neterminuje pre žiaden stav
- program má zmysel len pokiaľ skončí po konečnom počte krokov
- Príkaz $S_1$ je sémanticky ekvivalentný k príkazu $S_2$, ak pre všetky stavy $s$ a $s'$ platí: $$\langle S_1,s \rangle \rightarrow s'\ \ \ \ \text{iff}\ \ \ \  \langle S_2,s \rangle \rightarrow s'$$
- prirodzená sémantika jazyka je *deterministická* pokiaľ pre vykonaný príkaz $S$ v stave $s$ platí:$$\langle S,s \rangle \rightarrow s'\ \ \ \ \text{a}\ \ \ \  \langle S,s \rangle \rightarrow s''\ \ \ \ \text{, potom}\ s'=s''$$

Sémantická funkcia prirodzenej sémantiky je teda:
$$\text{S}_\text{ns} : Statm \rightarrow (State \rightharpoonup State)$$
Znamená to teda, že významom príkazu je teda zmena stavu. Nakoľko je [[Funkcie|čiastočne definovaná]], môžeme ju definovať:
![[prirodzena_sem_def.excalidraw]]
Symbol $\perp$ znázorňuje, že v danom prípade nie je sémantická funkcia definovaná, a teda vykonanie príkazu neposkytne stav:
$$
\text{S}_\text{ns}\ [[S]]s = \perp
$$

 



---
