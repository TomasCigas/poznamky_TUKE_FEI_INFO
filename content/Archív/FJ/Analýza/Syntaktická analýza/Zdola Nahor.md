# Zdola Nahor
Začína sa so vstupným reťazcom a aplikovaním pravidiel naopak sa snažíme dostať do začiatočného reťazca.

Môžeme si to predstaviť ako redukciu vstupného reťazca.

V každom kroku sa symbol na ľavej strane pravidla (**L**eft) nahradí pravú (**R**ight) stranu produkcie, preto **LR**. Existuje viacero prístupov, ktoré sú označované podobne ako [[Zhora Nadol|LL]]:
- **LR(0)** -> obmedzený počet použitelných gramatík, tabuľka [[#Riešenia|ACTION]] neobsahuje vstupný symbol
- **LR(1)** -> zahŕňa omnoho väčšiu škálu gramatík, avšak je zložitejší.
- **SLR(1)** a **LALR(1)** -> komplexitov a spektrom sa nachádzajú medzi LR(0) a LR(1), *S*LR = simple LR a LALR = look ahead LR.

**Výhody zdola nahor**:
- rozpoznáva takmer všetky programovacie jazyky
- najsilnejšia metóda bez backtrackingu pre shift-reduce
- chyby sa detekujú najskôr ako je to možné
**Nevhýhody zdola nahor**:
- náročná implementácia

Model:
![[LR_parser.excalidraw]]

## Analyzátor LR(1)
Syntaktický analyzátor bude na svojom výstupe generovať postupnosť pravidiel.

**Rukoväť**:
- podreťazec, ktorý zodpovedá pravej strane pravidla, ktorého redukcia predstavuje jeden krok odvodenia.
- je potrebná na korektný výber pravidla, pokiaľ existuje viacero možností.
- napr.:
	- Ak $S\Rightarrow ^{rm^*} \alpha A \omega \Rightarrow ^{rm} \alpha \beta \omega$
	- tak $A \rightarrow \beta$ je handle (rukoväť) reťazca $\alpha \beta \omega$

**Životaschopný prefix**:
- prefix pravej vetnej formy, ktorý nepresahuje pravý koniec (najpravejšej) handle vetnej formy

### Problémy
- **Nedeterminizmus**
	- presun možno vykonať kedykoľvek
	- redukcia podľa nejakého pravidla prichádza do úvahy vždy keď sa vo vstupe nachádza jeho pravá strana (aj keď to môže byť nevhodné)
- **Rozpoznávanie pravých strán pravidiel v zásobníku**
	- pravé strany môžu obsahovať viacero symbolov, ideálne by bolo, keby algoritmus musel rozpoznávať len 1 symbol  

#### Riešenia
- **Stavy**
	- do zásobníka nebudeme vkladať symboly, ale **stavy**, ktoré budú kódovať aké časti pravých strán pravidiel sa nachádzajú na vrchole teoretického zásobníka symbolov
	- syntaktický analyzátor bude na to potrebovať dve tabuľky:
		- *ACTION[s,t]* -> udáva typ [[Syntaktická analýza#Zdola nahor|akcie]], akú má program vykonať ak je na vrchu zásobníka stav *s* a na vstupe symbol *t* $\in T_\epsilon$ 
		- *GOTO[s,X]* -> udáva, aký nový stav sa uloží na vrch zásobníka, pokiaľ momentálny stav je *s* a do teoretického modelu by sa vkladal symbol *X*, $X\in N\cup T$