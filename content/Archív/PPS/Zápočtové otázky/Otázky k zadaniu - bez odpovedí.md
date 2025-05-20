*********************************
# Java
## Ako sa vytvárajú vlákna v programovacom jazyku Java?
- Vytvorením triedy, ktorá implementuje rozhranie Runnable a implementovaním metódy run()
- Použitím metódy start() z triedy Thread
- Vytvorením triedy, ktorá rozširuje triedu Thread a implementovaním metódy run()
- Vytvorením inštancie Runnable a jej prenesením do konštruktora triedy Thread
## Aký je hlavný rozdiel medzi implementáciou rozhrania Runnable a rozšírením triedy Thread pre vytvorenie vlákien?
- Implementácia rozhrania Runnable umožňuje triede dediť od inej triedy, čo je v Jave dôležité kvôli obmedzeniam jednej dedičnosti, zatiaľ čo rozšírenie triedy Thread to neumožňuje.
- Implementácia rozhrania Runnable je jednoduchšia na správu a flexibilnejšia v porovnaní s rozšírením triedy Thread.
- Rozšírenie triedy Thread je rýchlejšie ako implementácia rozhrania Runnable. 
- Implementácia rozhrania Runnable je odporúčaná pre jednoduchú spustiteľnú logiku, zatiaľ čo rozšírenie triedy Thread je vhodné pre zložitejšie scenáre viacvláknového programovania.
## Aká je úloha kľúčového slova synchronized v Jave?
- Zabezpečuje, že iba jedno vlákno má prístup k danému bloku kódu alebo metóde v jednom čase
- Umožňuje viacerým vláknam súčasne pristupovať k zdieľaným zdrojom 
- Zabezpečuje, že vlákno bude synchronizované so systémovým časom 
- Obmedzuje počet vlákien, ktoré môžu súčasne bežať v aplikácii ~Umožňuje vláknu čakať na splnenie určitej podmienky
## Ktorý stav vlákna naznačuje, že bolo spustené metódou start(), ale ešte nezačalo vykonávať svoju úlohu?
- Nový
- Spustiteľný 
- Zablokovaný 
- Ukončený 
- Čakajúci

# Python
## Ktorý z nasledujúcich príkazov v Pythone je používaný na vytvorenie procesu?
- threading.Thread() 
- multiprocessing.Process()
- os.getcwd() 
- os.chdir()
## Čo je to GIL (Global Interpreter Lock) v Pythone?
- Mechanizmus, ktorý umožňuje paralelné vykonávanie vlákien v Pythone. 
- Mechanizmus, ktorý umožňuje viacerým procesom zdieľať rovnakú pamäť. 
- Mechanizmus, ktorý zabraňuje súčasnému vykonávaniu viacerých Pythonovských vlákien.
- Nástroj, ktorý automaticky optimalizuje kód pre paralelné vykonávanie.
## Ako sa dá zdieľať pamäť pri paralelnom programovaní v Pythone?
- Použitím modulu multiprocessing.shared_memory
- Použitím modulu multiprocessing.Pool 
- Použitím modulu threading 
- Použitím modulu multiprocessing.manager
## Akými spôsobmi sa dajú paralelne spravovať úlohy v Pythone pomocou modulu multiprocessing?
- Použitím triedy Thread 
- Použitím triedy Process
- Použitím triedy Pool
- Použitím triedy multiprocessing na vytvorenie vlákien
# OpenMP
## Akými spôsobmi je možné nastaviť počet vlákien pri vykonávaní paralelného programu pomocou knižnice OpenMP?
- Pomocou direktívy: \#pragma omp parallel
- Cez premennú prostredia
- Pomocou runtime funkcie knižnice OpenMP
- Pomocou direktív
## Ktoré z uvedených direktív knižnice OpenMP zabezpečujú synchronizáciu?
- \#pragma omp critical. 
- \#pragma omp atomic.
- \#pragma omp master. 
- \#pragma omp single.
- \#pragma omp single nowait. 
- \#pragma omp barrier.
## Označ pravdivé tvrdenia ohľadom fungovania knižnice OpenMP
- Premenné, ktoré sú súkromné pre každé vlákno, sa ukladajú na heap. 
- Premenné, ku ktorým majú prístup všetky vlákna, sa ukladajú na heap. 
- Hodnota súkromnej premennej sa po skončení paralelného bloku automaticky zachová. 
- Pokiaľ sa neurčí explicitne typ premennej, tak premenná deklarovaná mimo paralelného bloku je verejná, vo vnútri bloku zas súkromná.

## Označ pravdivé tvrdenia ohľadom paralelizácie for cyklu pomocou knižnice OpenMP
- K direktíve cyklu sa nedá špecifikovať prístup k jednotlivým premenným. 
- Po vykonaní cyklu sekcie sa všetky vlákna zlúčia do tzv. master vlákna a môže sa vykonávať zvyšok sekvenčného kódu. 
- Nie je možné špecifikovať počet iterácií, ktoré má vykonať jedno vlákno. 
- Pomocou direktívy schedule(type, chunk) sa dá nastaviť, koľko iterácií má vykonať jedno vlákno.

# POSIX:
## Ktoré synchronizačné technológie podporuje POSIX?
- R/W Lock
- Synchronized
- Semafór
- Taskwait

## Ktoré argumenty sú nevyhnutné na tvorbu vlákna?
- Veľkosť pamäte na jedno vlákno
- Funkciu, ktorú bude vlákno vykonávať
- Argumenty funkcie
- Referenciu na dané vlákno

## Čo robí Mutex v POSIX v bode, kde ho uzamkneme
- Pošle signál všetkým vláknam o uzamknutí
- Blokuje prístup dokým sa mutex neodomkne
- Čaká dokým sa uzamknú všetky vlákna
- Pripočíta sa v jeho štruktúre počet uzamknutí

## Ako môžeme vrátiť hodnotu z funkcie vlákna
- Return na konci funkcie
- Do pthread_exit vložíme našu hodnotu
- Jeden z argumentov funkcie dedikujeme ako výsledok
- Nie je to možné

# CUDA
## Čo je to "kernel" v CUDA
- Funkcia, ktorá sa spúšťa na GPU
- Funkcia, ktorá sa spúšťa na CPU 
- Funkcia, ktorá sa spúšťa na oboch, CPU a GPU 
- Funkcia, ktorá sa spúšťa na žiadnom z nich

## Čo je to warp v CUDA?
- Skupina vlákien, ktoré bežia na jednom SM
- Skupina blokov vlákien, ktoré bežia na jednom GPU 
- Skupina GPU, ktoré bežia v jednej systémovej pamäti 
- Skupina systémových pamätí, ktoré bežia v jednom dátovom centre

## Čo je to "shared memory" v CUDA?
- Pamäť, ktorá je zdieľaná medzi všetkými vláknami v bloku
- Pamäť, ktorá je zdieľaná medzi všetkými blokmi vlákien na jednom GPU 
- Pamäť, ktorá je zdieľaná medzi všetkými GPU v systéme 
- Pamäť, ktorá je zdieľaná medzi všetkými systémami v dátovom centre
## Ktorá z nasledovných možností nie je funkciou CUDA wrapera pre alokáciu pamäte na GPU?
- cuda.alloc_global()
- cuda.alloc_shared() 
- cuda.alloc_constant() 
- cuda.alloc_local()
## Ktorá z nasledovných možností nie je príkladom použitia CUDA wrapera v reálnej aplikácii
- Webový vývoj
- Finančné modelovanie 
- Strojové učenie 
- Spracovanie obrazu

# C\#
## Ako sa volá knižnica poskytujúca API na paralelné programovanie v C#?
- Task Parallel Library (TPL)
- Parallel Programming framework 
- C# parallel toolkit 
- Multi-Threading Library
## Aké API poskytuje knižnica TPL v C# na vykonávanie paralelných operácií?
- Triedu `Task`
- Triedu `Parallel`
- PLINQ – Parallel LINQ
- Triedu `SleepTime`
## Čo je koncept Task-u v Task Parallel Library (C#)?
- Operácia s možnosťou sync/async/parallel vykonávania
- Operácia, ktorá sa nedá spustiť synchrónne 
- Operácia, ktorá sa nedá spustiť asynchrónne 
- Operácia, ktorá sa nedá spustiť paralelne
## Ktoré dátové štruktúry existujú v C# na účel paralelného programovania?
- public class ConcurrentQueue\<T>
- public class ConcurrentStack \<T>
- public class ConcurrentArray \<T> 
- public class ConcurrentObject \<T>

## OpenCL
## Ktoré z nasledujúcich patrí k výhodám OpenCL oproti podobným technológiám?
- Výpočty v heterogénnych prostrediach
- Vysoká miera abstrakcie 
- Častá hardvérová závislosť implementácii 
- Kompletná kontrola nad pamäťou a spôsobom výpočtov

## Čo je Kernel v kontexte OpenCL?
- Funkcia, ktorá vykonáva jednotlivý paralelný výpočet na výpočtovej jednotke
- Typ dátovej štruktúry dostupný pre jednotlivé vlákna paralelných výpočtov 
- Vrstva architektúry, ktorá synchronizuje vlákna paralelných výpočtov 
- Programovací jazyk na úrovni systému

## Ktoré synchronizačné techniky ponúka OpenCL?
- Semafór 
- Mutex 
- Bariéra v jednotlivej lokálnej pracovnej skupine
- Zdieľaný synchrónny Kernel

## Ako definujeme pracovné skupiny (workgroups) v OpenCL?
- Pomocou direktív prekompilátora 
- Argumentom funkcie 'clEnqueueNDRangeKernel'
- Vytvorením samostatného OpenCL kernelu 
- Modifikovaním zdrojového kódu OpenCL programu


*********************************