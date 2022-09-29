# Medzikód
**Medzikód** je forma reprezentácie pôvodného zdrojového programu po jeho sémantickej analýze.
- odďeľuje analýzu a generovanie kódu ( lepšia modularita )

**Kritéria medzikódu**:
- nedochádza ku strate informácií zo sémantického pohľadu
- reprezentácia musí byť bližšie ku strojovému jazyku ako pôvodný program

## Formy medzikódu
### Postfixný zápis
Umožňuje vyhodnocovanie výrazov len s pomocou zásobníka bez pomocných premien.
Postfixný zápis dostávame postorder prečítaním stromu odvodenia.
napr.:
$$
\begin{align}
a*b+c \\
ab*c+
\end{align}
$$

### Jazyk štvoríc
Je tvorený inštrukciami, ktoré sú svojím charakterom podobné inštrukciám strojových jazykov.
Operandy sú tvorené konštantami a premennými (nie registrami). Používajú sa aj dočasné premenné, konvenčne označované *t[názov]*.
Je abstraktný (operátor nemôže byť register, ktorý je závislý na platforme).

**Štvorica**:
$$
(operátor,operand1,operand2,výsledok)
$$


### Abstraktný syntatktický strom

