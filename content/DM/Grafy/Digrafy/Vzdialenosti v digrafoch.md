# Vzdialenosti v digrafoch

## Maticové reprezentácie grafov

### Matica incidencie
- rovnako ako pri [[Vzdialenosti v grafe#Matica incidencie|grafoch]], ale koncom sa dáva -1 a začiatkom 1

### Matica susednosti
- rovnako ako pri [[Vzdialenosti v grafe#Matica susednosti|grafoch]], ale zapisujú sa len [[Digrafy|začiatočné]] vrcholy 

### Diagonálna matica
- rovnako ako pri [[Vzdialenosti v grafe#Diagonálna matica|grafoch]], ale zapisujú sa len [[Digrafy|začiatočné]] vrcholy 

### Matica C
- výpoćet:
$$
C = D-B-B^T
$$
$$
C = A * A^T
$$
kde $D$ je diagonálna matica, $B$ je matica [[#Matica susednosti|susednosti]] a $A$ je matica [[#Matica incidencie|incidence]]