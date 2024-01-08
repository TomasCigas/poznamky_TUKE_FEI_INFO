***********
Paradigmy programovania slúžia na klasifikovanie jazykov a vyjadrenie ich funkcionality.

Niektoré programovacie jazyky sa skladajú aj z viacerých paradigiem.

## Imperiálne programovanie
*Príkazy* vykonávané v rozkazovacom štýle. Programovanie sa sústredí na sekvenciu postupností.

**Charakteristiky**:
- početné zmeny hodnôt uložených v pamäti
- samotné výpočty sú jednoduché
- [[Konštrukcie#Toky riadenia|tok riadenia]] je vyjadrený postupnosťou príkazov, podmienkami, cyklami a pod.
## Funkcionálne programovanie
Kladie dôraz na výpočty a oblasti [[Konštrukcie#Toky informácií|vidieľné väzby]], procedurálnu abstrakciu a jej aktiváciu.

**Charakteristiky**:
- obsahuje rozsiahle a komplexné výpočty hodnôt
- málo priradení hodnôt
- [[Konštrukcie#Toky riadenia|tok riadenia]] je vyjadrený aktiváciou funkcií
- viditeľnosť v deklaráciách je často rekurzívna
## Súbežné programovanie
Kladie dôraz na súbežné procesy, [[Konštrukcie#Toky riadenia|výber alternatívy]] a [[Konštrukcie#Toky informácií|odovzdávanie správ]].

**Charakteristiky**:
- každý proces vykonáva malé množstvo výpočtov
- alternatívy sa vykonávajú na základe synchronizácie či druhu správy
## OOP
Informácie o OOP boli preberané na predmete [[Objektovo orientované programovanie]].

Chápe sa ako [[#Imperiálne programovanie|imperatívne programovanie]] s pravidlami pre [[Konštrukcie#Toky informácií|vidieľné väzby]],

**Charakteristiky**:
- používa väzby medzi objektmi a metódami
- objekt je fragment pamäte buď ako inštancia, alebo na väzba na inštanciu
- metódy sú viazané k objektom

## Logické programovanie
Sústredí sa na ukladanie faktov a  [[Konštrukcie#Toky riadenia|výber alternatívnych možností]]  za účelom logických úkonov. Využívané na vedecké účely.

**Charakteristiky**:
- program pozostáva z alternatívnych procedurálnych abstrakcií
- výber alternatív sa robí pomocou *unifikácie vzorov* medzi parametrami abstrakcií a argumentmi aktivácie funkcie. Táto unifikácia sa viaže identifikátormi k termom

---