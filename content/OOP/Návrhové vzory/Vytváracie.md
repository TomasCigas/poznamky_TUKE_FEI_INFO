# Vytváracie návrhové vzory
Zaoberajú sa vytváraním a klasifikovaním objektov a tried.

## Factory method
- 
## Singleton
- používa sa pokiaľ chceme aby trieda mala iba jeden objekt
- konštruktor nastavíme na privátny, teda nebudeme môcť vytvoriť nový objekt zavolaním konštruktora
- potom len vytvoríme verejnú funkciu ktorá nám buď vytvorí tento objekt, pokiaľ neexistuje a potom nám ho vráti
	- táto funkcia musí byť však statická, keďže zo začiatku nebude existovať objekt, nad ktorým by sme mohli zavolať túto funkciu. 
- príklad použita:
```java
public class Logger{
	private static Logger logger
	
	private Logger(){
	}
	
	public static Logger getInstance(){
		if(logger == null){
			logger = new Logger();
		}
		return logger;
	}
}
//testing logger
public class TestLogger{
	Logger obj1 = Logger.getInstance();
	Logger obj2 = Logger.getInstance();
	// obj1 == obj2	
}
```
- ! pokiaľ vytvoríme dve triedy TestLogger objekty Logger medzi týmito TestLoggermi už nebudú rovnaké




