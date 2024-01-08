***********
Programovacie jazyky môžu byť typované:
- **staticky** $\rightarrow$ typovanie je uvedené v programe
- **dynamicky** $\rightarrow$ typovanie prebieha počas fungovania programu

Formálna definícia jazyka:
- syntax
- sémantika

Formálnu syntax môžeme definovať:
- [[Gramatika|gramatikou]]
- [[Lexikálna analýza#Backusova-Naurova forma|BNF]] produkčným pravidlom
- induktívnou definíciou
	- definuje množinu legálnych termov ako najmenšiu mnozinu $Term$
- odvodzovacími pravidlami

Jazyky pozostáva z *termov*, ktoré reprezentujú základné syntaktické konštrukcie.

# Typovanie
Typovanie je proces priradzovania [[Typy|typu]] termu.
Formálne definujeme typovanie prostredníctvom **typovacími pravidlami** a **typovacou reláciou**.

Typovacia relácia pre T-NBL:
$$
\fbox{$t : T$}
$$


Kontrola typu prebieha tvorbou stromu, kde:
- koreň je dole a obsahuje kontrolovaný term
- každý vrchol obsahuje typovacie pravidlo
- listy sú axiómy

Term $t$ je správne typovaný ak existuje nejaký typ $T$, ktorý by bol typom termu $t$.

Pri typovaných jazykoch skúmame:
- **Jednoznačnosť**: každý správne typovaný term má *práve* jeden typ
- **Bezpečnosť** obsahuje 2 podvlastnosti:
	- platí **progresia**: správne typovaný term je buď hodnota alebo redukovateľný
	- platí **stabilita**: vyhodnotenie zachováva typy (počas vyhodnotenia sa nemení)

## Curryho a Churchov štýl vyhodnotenia a typovania

[[Jednoducho typovaný lambda-kalkul|JTLK]]  bol nezávisle formulovaný Churchom a Currym. Obidvaja definovali formuláciu sémantiky iným spôsobom:

**Curry** - Vyhodnotenie pred typovaním:
1. syntax
2. vyhodnotenie
3. typovanie
4. stále má zmysel hovoriť o výsledku termu

Church - Typovanie pred vyhodnotením (Church - podľa kostolného poriadku):
1. syntax
2. typovanie
3. vyhodnotenie
4. nesprávne typované termy nemá zmysel vyhodnocovať
# Detypovanie
Pri vyhodnocovaní programu dochádza k odstráneniu typov, nakoľko ak už zbehla kontrola typov, tieto typy už nie sú ďalej potrebné. Teda program sa prevedie naspäť do netypovaného stavu:
$$
\begin{gather}
erase(x:T) = x\\
erase(\lambda x:T_1.t_2) = \lambda x.erase(t_2)\\
erase(t_1\ t_2) = erase(t_1)\ erase(t_2)
\end{gather}
$$

Na poradí detypovania pri správne typovaných programoch nezáleží kvôli *Vete o komutatívnosti vyhodnotenia a typovania*.

Z detypovania vyplíva, že dokážeme detypovanie pri správne typovanom terme vrátiť naspäť (taktiež vďaka jednoznačnosti jazyka).

Zavedieme teda **typovateľnosť termu** - netypovaný term $m$ je **typovateľný**, ak platí:
- existuje jednoducho typovaný term $t$
- existuje typ $T$
- existuje typový kontext $\Gamma$, taký, že: $erase(t) = m$ a $\Gamma \vdash t : T$

Typovateľnosť sa využíva pri [[Typy#Typová rekonštrukcia|rekonštrukcii typov]].

---
- [[Lambda-kalkul]]
- [[NBL]]
- [[Výnimočné situácie]]
---