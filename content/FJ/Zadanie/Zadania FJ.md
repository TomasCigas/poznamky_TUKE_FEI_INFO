# Zadanie 1
Regulárny výraz: ({a}|bc)b[c]{a|b},
DKA a diagramy:
![[DKA_zadanie.excalidraw]]

# Zadanie 2
**Kalkulačka**

Gramatika:
E -> T { ('+' | '-') T }
T -> F { ('\*' | '/') F }
F -> ['-'] Q
Q -> celé číslo | '( E )'
