# Zhora Nadol

Začína sa zo štartovacieho symbolu a postupuje sa smerom k listom.
Vyberie sa pravidlo z gramatiky a pokúsi sa spracovať aktuálny vstup.

[[Gramatika|Gramatiky]], ktoré je možné analyzovať zhora nadol, čítaním vstupu zľava (**L**eft) a uplatňovaním najľavejšieho odvodzovania (**L**eft) sa nazývajú gramatiky **LL**.
Označenie LL**(1)** znamená, že odvodenie za použitia pravidla je možné urobiť na základe jedného (1) symbolu na vstupe. Analogicky **(k)** je odvodenie na základe **k** symbolov.

Takáto gramatika je deterministická, viac rozpísané nižšie pri [[#Analyzátor LL 1|analyzátore]].

## Analyzátor LL(1)
Rozhoduje, ktoré pravidlo sa využije na expanziu v teoretickom modely, pokiaľ existuje viac pravidiel na jeden neterminál.

Analyzátor má predurčené usporiadané dvojice $(A,t)$, kde $A$ je pravidlo a $t$ je vstupný symbol.

Toto predurčenie sa znázorňuje ako *rozkladová tabuľka*.
V prípade, že neexistuje pravidlo pre určitý vstup automat vyhodí syntaktickú chybu.
napr.:

--|a|b|c|\$
--|--|--|--|--
S|1|--|--|1
A|2|--|--|--
B|--|4|--|--

je LL(1) parsovanie a

--|a|b|\$
--|--|--|--
S|1|1|1
A|2|3,4|--
B|--|5,6|--

nie je, pretože automat sa nevie presne rozhodnúť v niektorých prípadoch.

Nie každá [[Gramatika#Klasifikácia|bezkontextová gramatika]] je LL(1) gramatika (ako môžeme vidieť na rozkladových tabuľkách vyššie).

Dokážeme však takúto gramatiku upraviť, najčastejšie konflikty:
- spoločné [[Formálne jazyky#Abeceda|predpony]]
- ľavá rekurzia

### Odstránenie ľavej rekurzie
Ľavá rekurzia je v gramatike vtedy, ak pre neterminál $A$ existuje odvodenie:

$A \Rightarrow ^+ A\beta$, tak A nazývame rekurzívny zľava
$A \Rightarrow ^+ \alpha A$, tak A nazývame rekurzívny sprava

Takáto gramatika sa nazýva **rekurzívnou**.

Pokiaľ je v gramatike aspoň jedno pravidlo:
$A \rightarrow A\alpha$, kde $A\in N$ a $\alpha \in (N\cup T)$
Tak gramatika sa nazýva **gramatika s priamou ľavou rekurziou**.

Takúto gramatiku dokážeme premeniť na pravú rekurziu:
*Ak*:
$A \rightarrow A\alpha _1 | A\alpha _1 | ... | A\alpha _m | \beta _1 | \beta _2 | ... |\beta _n$
pri čom neterminál $A$ nie je predponou ani jedného z reťazcov $\beta$, potom je možné nahradiť všetky pravidlá:
$A \rightarrow \beta _1 | \beta _2 | ... |\beta _n | \beta _1 A'| \beta _2 A'| ... |\beta _n A'$
$A' \rightarrow \alpha _1 | \alpha _2|...|\alpha _m| \alpha _1 A' |\alpha _2 A' |...|\alpha _m A'$
kde $A'$ je nový terminálny symbol.
