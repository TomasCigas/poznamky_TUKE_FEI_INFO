# Vlastnosti digrafov

## Stupeň vrchola
- [[Vlastnosti grafov#Stupeň vrchola v grafe|stupeň]] vrchola môže byť vonkajší a vnútorný:
	- vonkajší -> počet vrcholov, pre ktorý je tento vrchol začiatkom
	- vnútorný -> počet vrcholov, pre ktorý je tento vrchol koncom

## Slabá a silná súvislosť
- [[Digrafy|digraf]] je **slabo súvislý** pokiaľ jeho [[Vlastnosti grafov#Súvislosť|súvislosť]] **nespĺňa** orientáciu
- digraf je **silne súvislý** pokiaľ jeho súvislosť **spĺňa** orientáciu, teda ak medzi každou dvojicou vrcholov existuje [[Postupnosť vrcholov a orientovaných hrán#Dráha|dráha]]

## Koreňová kostra
- pre nájdenie koreňových kostier postupujeme ako pri [[Vlastnosti grafov#Kostra|normálnom grafe]], však na začiatku vyradíme riadok a stĺpec korešpundujúceho vrchola, ktorý si ako koreň zvolíme
- pokiaľ však chceme nájsť celkový počet kostier, môžeme vytvoriť [[Vzdialenosti v digrafoch#Matica C|maticu C]] alebo vytvoríme matice susednosti a diagonálnu bez orientácie 
