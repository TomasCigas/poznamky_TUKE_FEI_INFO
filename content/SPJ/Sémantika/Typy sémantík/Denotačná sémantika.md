*********************************
Denotačná sémantika priraďuje k syntakticky správnemu programu jeho jednoznačný význam - **denotáciu programu**. DS je **kompozičná**, teda denotácia zložitého prvku je definovaná **len** podľa jeho prvkov

Význam je programov vyjadruje pomocou funkcií a čísel.

**Denotácia programu** dosiahne výsledok bez ohľadu na poradie vykonania.

Denotácia **podmienky**:
- zo syntaxe:
![[Pasted image 20240121202552.png]]
- definícia pri stave:
![[Pasted image 20240121202544.png]]
- komplet:
![[Pasted image 20240121202619.png]]

Denotácia **cyklu**:
- nemôžeme použiť $cond$ nakoľko by sme narušili **kompozičnú vlastnosť** denotácie
- potrebujeme dostať [[Lambda-kalkul#Fixný bod a rekurzia|fixný bod]] cyklu a postupne dopĺňame jednotlivé časti cyklu:
1. ![[Pasted image 20240121203141.png]]
2. ![[Pasted image 20240121203149.png]]
3. ![[Pasted image 20240121203158.png]]
!Dôkaz medzi vzťahom denotačnej sémantiky a operačnej sémantiky je bolestivý a nikto by sa ho nikdy nemal učiť, nech žije v hrobe ľudí, čo ho stvorili. Jeho princípom je dôkaz sémantickej ekvivalencie medzi všetkými príkazmi.


# Nepriama denotačná sémantika
Nepriama denotačná sémantika rozširuje denotačnú sémantiku o spôsob zmeny [[Konštrukcie#Toky riadenia|toku riadenia]] a pokračovanie vyhodnotenia programu aj v prípade chyby.

Najznámejšie vlastnosti NDS:
- ukončenie programu - $\texttt{stop}$
- výnimočné situácie - $\texttt{exception}$
- nepodmienený skok - $\texttt{goto}$

Zmenu toku riadenia popisuje funkcia:
$$
c \in Continuation = State \rightharpoonup State
$$

Princípy:
- $c$ vyjadruje zmenu stavu pri vykonaní zvyšku programu
- Argument $c$ je stav programu v danom okamihu
- Hodnota $c$ je stav, v ktorom sa skončí vykonanie celého programu

Sémantika je podobná priamej denotačnej s rozdielmi:
- **Postupnosť** - vykonáva sa v opačnom poradí:
![[Pasted image 20240122191752.png]]

Výnimočné situácie:
- vykonáva sa handler pri $raise$
![[Pasted image 20240122191920.png]]

![[Pasted image 20240122192022.png]]
![[Pasted image 20240122192026.png]]
Po $raise$ pokračuje program normálne, len sa pomedzi to spracuje výnimočná situácia

Skok - skočí len na miesto, kde je $label$



*********************************