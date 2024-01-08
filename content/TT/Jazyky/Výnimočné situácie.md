***********
Výnimočné situácie môžu nastávať v programoch v prípade, že sa snažíme vyhodnotiť term, ktorý nemá logický význam (napr. delenie 0).

Nechceme avšak, aby v prípade výnimočnej situácie náš program prestal fungovať a len sa presunul na ďalšiu časť výpočtu. Preto sa využíva tzv. **handler výnimočných situacií**, ktorý zabezpečuje *spracovanie* výnimočnej situácie. *Signalizovanie* prichádza od samotného programu

Na lepšie zistenie dôvodu výnimočnej situácie sa obvykle aj vymieňajú dáta medzi signalizovaním a handlerom.

V prípade [[Jednoducho typovaný lambda-kalkul|JTLK]] môžeme rozšíriť syntax o term $error$, ktorá bude značiť výnimočnú situáciu v programe a signalizuje tak chybu.

Takýto term sa bude vyhodnocovať spôsobom, že sa zbaví všetkých hodnôt a termov okolo seba:
![[Pasted image 20240108151750.png]]

Vyhodnotenie $error$ zapríčiní, že sa aktivačný záznam nerozvinie a postupne sa obsah zásobníka aktivačných záznamov vyprázdni, dokým neostane len $error$:
![[Pasted image 20240108151912.png]]

[[Typy|Typ]] termu $error$ závisí od druhu jazyka, v ktorom sa vykonáva:
- v jazyku s **podtypmi** priradíme termu najmenší typ $\perp$, ktorý môže byť povýšený na ľubovoľný typ
- v jazyku s **polymorfizmom** zadáme termu polymorfný typ $\forall X.X$, ktorý bude inštanciovaný na ľubovoľný iný

Veta o [[Jazyky#Typovanie|progresii]] musí byť rozšírená o term $error$ nakoľko tento term sa nedá redukovať ďalej. Inak povedané:
Ak je term $t$ správne typovaný a neredukovaťeľný, potom $t$ je buď hodnota, alebo $error$.

**Spracovanie** tejto výnimočnej situácie sa obvykle robí prostredníctvom handlera, ktorý zabezpečuje, že v prípade $error$ termu sa vykoná "záložná časť" programu:
$$
\texttt{try} \ t_1\ \texttt{with}\ t_2
$$
Teda vyhodnotí sa najprv $t_1$ a ak neexistuje z tohto termu hodnota sa vykoná term $t_2$.

Ako bolo spomínané vyššie v prípade, že chceme preniesť hodnoty do handlera potrebujeme určiť aká informácia sa prenesie. Napríklad si môžeme rozšíriť [[Jednoducho typovaný lambda-kalkul|JTLK]]:
$$
\texttt{raise}\ t_3\ \text{a}\ \texttt{try}\ t_1\ \texttt{with}\ t_2
$$
Kde $\texttt{raise}\ t_3$ môžeme chápať ako signalizáciu (namiesto $error$), ktorá odovzdá informáciu $t_2$, alebo inak povedané sa stane jej argumentom:
$$
\texttt{try}\ \texttt{raise}\ t_3\ \texttt{with}\ t_2 \rightarrow t_2\ t_3
$$




---