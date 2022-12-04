************************************
**CO**nstructive **CO**st **MO**del je algoritmický odhad nákladov na vytvorenie softvéru
Tento model používa základné regresné funkcie s hyperparametrami derivované z minulých [[Metrika|meraní]] a projektov.

Existuje viacero verzií

# COCOMO 81
Podľa vývojového módu sa delí na:
- *Organic*
	- malé tímy s dobrými skúsenosťami a voľnejšími požiadavkami
- *Semidetached*
	- stredné tímy s miešanými skúsenosťami a miešanými požiadavkami
- *Embedded*
	- vývoj s prísnymi obmedzeniami, kombinované prvky *organic* a *semidetached* projektov

A podľa modelu na:
## Basic
- rýchly a celkom nepresný spôsob odhadu, kvôli nedostatku faktorov a informácií
- *Effort* sa počíta z veľkosti programu
## Intermediate
- rozšírenie *basic* o "Cost Drivers", čo sú upresnenia o vývoji projektu

**Cost Drivers**: 
- *Produktové atribúty*:
	- požadovaná spoľahlivosť softvéru
	- veľkosť databázy
	- komplexita produktu
- *Hardvérové atribúty*:
	- obmedzenia run-time
	- obmedzenia pamäte
	- nespoľahlivosť VM prostredia
	- požadovaný čas obratu (čas potrebný na vykonanie procesu)
- *Atribúty personálu*:
	- schopnosti analýzy
	- SW schopnosti
	- aplikácné skúsenosti
	- VM skúsenosti
	- programovacie skúsenosti
- *Projektové atribúty*:
	- používanie SW nástrojov
	- SW inžinierske metódy
	- požadovaný vývojový plán

Všetky tieto atribúty sú ohodnotené na škále od 1 po 6 (very low - extra high), avšak kvôli nedostatku dát sú niektoré z hodnotení spojené do jedného. Výsledok vynásobenia všetkých Cost Drive atribútov sa nazýva EAF. Obvykle sa pohybuje okolo 0.9 až 1.4
![[cost_drives.png]]

Pri *intermediate* COCOMO modely môžeme potom dostať celkový *effort*, trvanie a počet ľudí pomocou vzorcov:
![[COCOMO_int.png]]

## Detailed
- započítava vplyv jednotlivých fází projektu na *[[#Intermediate|Cost drive]]*, preto v detailnom modely nie je rozvrh nikdy statický.

**Detailný COCOMO** pozozstáva z 5 častí:
- Plánovanie a požiadavky
- Systémový dizajn
- Detailný dizajn
- Modulové kódenie a testovanie
- Integrácia a testovanie




# COCOMO II
Podľa modelu:
- *Application composition*
- *Early design*
- *Postarchitecture*
Škálovatelné faktory:
- *PREC*
- *FLEX*
- *RESL*
- *TEAM*
- *PMAT*
