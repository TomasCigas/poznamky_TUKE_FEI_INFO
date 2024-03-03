***********
Medzi niektorými logickými a výpočtovými systémami existuje korešpondencia (podobnosť), taktiež nazývaný aj **izomorfizmus**.

V prípade typového funkcionálneho programovacieho jazyka a intuitionistickej logiky existuje **Curryho-Howardova korešpondencia** (ďalej CHK).

**Intuicionistická logika** je typ logiky, ktorý sa ad klasickej logiky líši dvoma základnými vlastnosťami:
- zákaz dôkazu sporom
- nutnosť konštrukcie dôkazu a niektoré ďalšie dôkazy

Curry a Howard dokázali, že:
- **[[Jednoducho typovaný lambda-kalkul|typ jednoduchého typovaného LK]]** korešponduje s *dôkazom výroku* intuicionistickej logiky
- **[[Lambda-kalkul#Vyhodnotenie|Výpočet (redukcia termov)]]** korešponduje s **dôkazom výrokovej formuly**

Teda na CHK sa odvolávame v lituratúre použitím *paradigiem*:
- výroky_ako_typy
- dôkazy_ako_programy

Táto korešpondencia je jednoducho vyjadrená tabuľkou:

| Logika | Programovacie jazyky |
| ---- | ---- |
| výroky | typy |
| $P \Rightarrow Q$ | $P \rightarrow Q$ |
| $P \wedge Q$  | $P \times Q$ |
| $P \vee Q$ | $P + Q$ |
| dôkaz výroku $P$ | term $t$ typu $P$ |
| výrok $P$ je dokázateľný | $\exists$ vypočítateľný term typu $P$ |


---