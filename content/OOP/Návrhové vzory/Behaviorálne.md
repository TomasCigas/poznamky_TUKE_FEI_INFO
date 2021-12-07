# Behaviorálne návrhové vzory

## Strategický vzor
- spočíva v kapsulovaní algoritmov a separovaní ich od tried, v ktorých sa používajú
- jeho výhodou je znovapoužívanie algoritmov medzi podtriedami supertried
	- niekedy môžeme dosiahnúť aj úplné zrušenie podtried a nahradiť ich kombináciou kapsulovaných algoritmov
- UML na zobrazenie:
```mermaid
classDiagram

class Client{
IBehaviour ibehaviour
execute()}

class IBehaviour{
run()
}

class ConcreteBehaviourA{
run()
}

class ConcreteBehaviourB{
run()
}

Client-->IBehaviour

IBehaviour<|--ConcreteBehaviourA
IBehaviour<|--ConcreteBehaviourB

```

## Sledovatelský vzor
(Observer Pattern)
- používa sa ak chceme niektoré objekty (sledovatľov) upozorniť o zmene stavu určitého objektu (sledovanca)
- sledovanec má svoju skupinu sledovateľov, ktorých po zmene, resp. nadobudnutí určitého stavu informuje
- UML diagram:
```mermaid
classDiagram

class IObservable{
IObserver observers
add(IObserver)
remove(IObserver)
notify()
}

class IObserver {
update()
}

class ConcreteObservable{
IObserver observers
add(IObserver)
remove(IObserver)
notify()
}

class ConcreteObserver{
update()
}

IObservable-->"0..*"IObserver

IObservable<|--ConcreteObservable
IObserver<|--ConcreteObserver
```
- !pozor, z tohto diagramu vychádza však, že aj keď je sledovateľ oznámený o zmene stavu sledovanca, nemusí presne vedieť čo a ako sa zmenilo, preto je možné dať v konštruktore referenciu na sledovanca:
```mermaid
classDiagram

class IObservable{
IObserver observers
add(IObserver)
remove(IObserver)
notify()
}

class IObserver {
update()
}

class ConcreteObservable{
IObserver observers
add(IObserver)
remove(IObserver)
notify()
}

class ConcreteObserver{
IObserver observer
update(IObserver)
}

IObservable-->"0..*"IObserver

IObservable<|--ConcreteObservable
IObserver<|--ConcreteObserver

ConcreteObserver-->ConcreteObservable
```
- !pozor, podľa kódu je možné, že sledovanec bude samostatný objekt, ktorý vykonáva svoju činnosť a taktiež slúži ako sledovanec, ktorý informuje svojich sledovateľov, jednoducho povedané náš ConcreteObserver bude porušovať [[Princípy programovania#Princíp jednej zodpovednosti|princíp jednej zodpovednosti]]
	- je možné to napríklad zmenou IObservable z rozhrania na abstraktnú triedu a implementovania jednotlivých služieb zodpovedných za správu sledovateľov do nej