***********
Sémantika programu sa dokáže robiť rôznymi spôsobmi. Najzakladenejšie typy sémantiky sú:
- Sémantika [[Sémantika#Výrazy|výrazov]], ktorá zisťuje hodnotu výrazu
- Sémantika [[Sémantika#Stav|stavov]], ktorá pracuje s hodnotou výrazu v istom stave

# Viditeľnosť
Podľa úrovní viditeľnosti určujeme tieto typy sémantík:
- Dynamická
- Statická
- Kombinovaná

## Dynamická sémantika
Dynamická sémantika používa dynamické pravidlá viditeľnosti pre [[Konštrukcie#Procedúry|procedúry]] aj pre premenné.

Predchodcom zavolania procedúry je priradenie názvu procedúry k jej telu. Z toho dôvodu potrebujeme ďalšiu oblasť prostredia, do ktorej sa budú ukladať všetky procedúry:
$$
envp \in \texttt{Envproc}=\texttt{Procname} \rightharpoonup \texttt{Statm}
$$
Teda prostredie $envp$ bude obsahovať deklaráciu procedúr a aj ich priradených kódov.

Z toho dôvodu sa zmení aj tvar vyhodnotenia prostredníctvom [[Prirodzená sémantika|prirodzenej sémantiky]]:
$$
envp \vdash \langle S,s \rangle \rightarrow s'
$$
, čo teda znamená: *Vykonanie príkazu $S$ v stave $s$ v prostredí procedúr $envp$ nám poskytne výsledný stav $s'$*

## Statická sémantika
Statická sémantika používa statické pravidlá viditeľnosti pre [[Konštrukcie#Procedúry|procedúry]] aj pre premenné.
Využíva lineárnu pamäť, kde všetky hodnoty majú svoju pozíciu $l$ a ďalšiu sa priradí za danú pozíciu.

## Kombinovaná sémantika
Kombinovaná sémantika používa statické pravidlá viditeľnosti pre [[Konštrukcie#Procedúry|procedúry]] a statické dynamické pre premenné.

Kvôli statickej viditeľnosti procedúr, kde sa k názvu procedúry už rovno priradí aj jej telo už pri deklarácii procedúry musíme pozmeniť definíciu prostredia:
$$
\texttt{Envproc}=\texttt{Procname} \rightharpoonup \texttt{Statm} \times\texttt{Envproc}
$$

# Cheatsheet  sémantík
Ako vyzerajú jednotlivé sémantiky pre príkaz:
$$
x :=1;\texttt{if iszero(}x\texttt{) then }x:=x+1\texttt{ else }x:=x-1
$$
## Prirodzená
![[prir.excalidraw]]

## Štrukturálna operačná
![[str_op.excalidraw]]
## Denotačná
![[Denot.excalidraw]]

# Sémantika abstraktného stroja

![[ABS_ss.excalidraw]]



---
- [[Operačná sémantika]]
- [[Prirodzená sémantika]]
- [[Štrukturálna operačná sémantika]]
- [[Denotačná sémantika]]
- [[Axiomatická sémantika]]
- [[Algebraická sémantika]]
---