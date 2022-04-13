# DKA
## 1
![[DKA1.excalidraw]]

# Gramatika
G = ({S,A,B},{a,b,c},P,S)
_S → BAB | ABA_  
_A → AB | aA | ab_  
_B → BA | b_

Dosiahnite **abbbab**

S => ABA -> ABBA -> abBBab -> abbBab -> abbbab

# Lexikálna analýza
## 1
E -> T { (+ | -) T}
T -> M { (\* | /) M }
F -> cislo | id | (E)

**Doplň o unárne mínus:**

E -> T { (+ | -) T}
T -> M { (\* | /) M }
M -> [-] F
F -> cislo | id | (E)

**Doplň o operáciu mocniny "\^" a operáciu zvyšku po delení "%":**

**Mocnina**
E -> T { (+ | -) T}
T -> M { (\* | /) M }
M -> [-] F
Q -> Q [\^ E]
F -> cislo | id | (E)

**Modulo**
E -> T { (+ | -) T}
T -> M { (\* | / | %) M }
M -> [-] F
Q -> Q [\^ Q]
F -> cislo | id | (E)

## 2
\*, +, -, /

E -> T [ (+ | - | / | \*) T  ]
T -> číslo | id | E

# Lexikálna analýza, gramatika

## 1
EBNF
E -> T {'\*' T}
T -> F ['+' T]
F -> id | '( E )'

Konvertovanie do BNF:
E -> T '\*' T | T
T -> F '+' T | F
F -> id | '( E )'

Strom:
$id + [id + id] * id * id$
$[id + x] * id * id$
$[x * id] * id$
$[x * id]$
![[FJ-strom.excalidraw]]

# Syntaktická analýza
## 1

S -> AB
A -> xB | $\epsilon$
B -> yA | zB

### 1
Terminály: x,y,z
Neterminály : S,A,B

### 2
**y**:
S => AB -> $\epsilon$B -> B -> yA -> y$\epsilon$ -> y

**zy**:
S => AB -> zB -> zyA -> zy

**xyy**:
S => AB -> xBB -> xyAB -> xyB -> xyyA -> xyy

**xyxzyy**:
S => AB -> xBB -> xyAB -> xyxBB -> xyxzBB -> xyxzyAB -> xyxzyB -> xyxzyyA -> xyxzyy

### 3
**S => xyyA**
S => AB -> xBB -> xyAB -> xyB -> xyyA
**Strom odvodenia**:
![[Strom-FJ6.excalidraw]]


### 4
**3 je pravá či ľavá?**
Ľavá derivácia

### 5
Uveďte príklad čiastočnej derivácie z **S** v dvoch krokoch pomocou pravej derivácie
S => AB -> AzB -> AzzB
S => AB -> AyA -> AyxB

### ex
**xyzy:**
S => AB -> AzB -> AzyA -> Azy -> xBzy -> xyAzy -> xyzy
**yxzy:**

## 2
S -> Bb | Cd
B -> aB | $\epsilon$
C -> cC | $\epsilon$

F => FIRST
F(S) = {a,b,c,d}
F(B) = {a,$\epsilon$}
F(C) = {c,$\epsilon$}

W => FOLLOW
W(S) = {$}
W(B) = {b}
W(C) = 

-------

S -> ABCDE
A -> a | $\epsilon$
B -> b | $\epsilon$
C -> c
D -> d | $\epsilon$
E -> e | $\epsilon$

F(S) = {a,b,c}
F(A) = {a,$\epsilon$}
F(B) = {b,$\epsilon$}
F(C) = {c}
F(D) = {d,$\epsilon$}
F(E) = {e,$\epsilon$}

W(S) = {$}
W(A) = {b,c}
W(B) = {c}
W(C) = {d,e,\$}
W(D) = {e,\$}
W(E) = {\$}

E -> TE'
E' -> TE | E
T -> FT'
T' -> FT' | $\epsilon$
F -> id | ( E )

F(E) = 
F(E') = 
F(T) = {id, '(' }
F(T') = {id , '(' }
F(F) = {id, '(' }

## DU
A -> AC
B -> Ax | x
C -> yC | y

## Slepé srandy na hodine

E -> TE'
E' -> TE' | d
T -> FT'
T' -> xFT' | $\epsilon$
F -> E | id

FIRST = F
F(E) = 
F(E') = 
F(T) = 
F(T') = 
F(F) = 

# Bextontextové gramatiky, LL parsovanie
## 1

1) S -> A#
2) A -> xAx
3) A -> C
4) B -> yBy
5) B -> C
6) C -> zBz
7) C -> wAw
8) C -> $\epsilon$

### N,T
Terminály = {#,x,y,z,w}
Neterminály = {S,A,B,C}

### Skonštruuj xzzx# začínajúc v S

S -> A# -> xAx# -> xCx# -> xzBzx# -> xzCzx# -> xzzx#

![[Drawing 2022-04-06 09.22.31.excalidraw]]

### First a Follow
FIRST(S) = {x,z,w,#}
FIRST(A) = {x,z,w,,$\epsilon$}
FIRST(B) = {y,z,w,,$\epsilon$}
FIRST(C) = {z,w,$\epsilon$}

FOLLOW (S) = {\#}
FOLLOW (A) = {\#,x,w}
FOLLOW (B) = {y,z}
FOLLOW (C) = {\#,x,w,y,z}

### Predict
![[Drawing 2022-04-06 09.37.24.excalidraw]]

PREDICT( **1** ) = {x,z,w,\#}
PREDICT( **2** ) = {x}
PREDICT( **3** ) = {z,w,\#,x}
PREDICT( **4** ) = {y}
PREDICT( **5** ) = {z,w,\#,x,y}
PREDICT( **6** ) = {z}
PREDICT( **7** ) = {w}
PREDICT( **8** ) = {\#,x,w,y,z}

### Zostavte rozkladovú tabuľku pre danú gramatiku. Zistite, či daná gramatika je LL(1) gramatikou

--|x|y|w|z|\#
---|---|---|---|---|---
S|1|--|1|1|1
A|2,3|--|3|3|3
B|5|4,5|5|5|5
C|8|8|7,8|6,8|8

## 2
1) S -> AB\#
2) A -> xA
3) A -> B
4) B -> yzB
5) B -> z

### First a Follow
FIRST(S) = {x,y,z}
FIRST(A) = {x,y,z}
FIRST(B) = {y,z}

FOLLOW(S) = {\#}
FOLLOW(A) = {y,z}
FOLLOW(B) = {\#,y,z}

### Predict
PREDICT( **1** ) = {x,y,z}
PREDICT( **2** ) = {x}
PREDICT( **3** ) = {y,z}
PREDICT( **4** ) = {y}
PREDICT( **5** ) = {z}

--|x|y|z|\#
--|--|--|--|--
S|1|1|1|--
A|2|3|3|--
B|--|4|5|--
Je to LL(1)

## 3
1) S -> A\#
2) A -> (AB)
3) A -> $\epsilon$
4) B -> (A)
5) B -> x

### First a Follow
FIRST(S) = { (, \# }
FIRST(A) = { (, $\epsilon$ }
FIRST(B) = { x, ( }

FOLLOW(S) = {\#}
FOLLOW(A) = { \#, ), x, (  }
FOLLOW(B) = { ) }

### Predict
PREDICT( **1** ) = { (, \# }
PREDICT( **2** ) = { ( }
PREDICT( **3** ) = { \#, ), x, ( }
PREDICT( **4** ) = { ( }
PREDICT( **5** ) = { x }

--|(|)|x|\#
--|--|--|--|--
S|1|--|--|1
A|2,3|3|3|3
B|4|--|5|--

Nie je LL(1), dochádza ku konfliktu.

## 4
1) S -> AB\#
2) A -> xA
3) A -> B
4) A -> $\epsilon$
5) B -> yzB
6) B -> z

### First a Follow
FIRST(S) = {x,y,z}
FIRST(A) = {x,z,y,$\epsilon$}
FIRST(B) = {z,y}

FOLLOW(S) = {\#}
FOLLOW(A) = {z,y,x}
FOLLOW(B) = {\#,x,y,z}