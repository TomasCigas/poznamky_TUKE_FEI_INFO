# Adresácia

## IP adresa
Adresa siete. Zvyčajne reprezentuje (ako na pošte) jednotlivé časti pozície zariadenia.

### IPv4
**IPv4** je 32 bitové číslo, v ľudskom formáte sa to zapisuje ako 4 čísla oddelené bodkov:
XXX.XXX.XXX.XXX

Každá časť sa volá **oktét**.

#### Triedy IP
Trieda|1. oktét|Maska|Sieťové a hostové rozdelenie
---|---|---|---
A|0-127|/8|S.H.H.H
B|128-191|/16|S.S.H.H
C|192-223|/24|S.S.S.H

Multicasting a broadcasting
#add_info 

### Maskovanie
**Maska** slúži na identifikáciu sieťove ja hostovej časti [[#IPv4]] adresy.

V realite je to postupnosť **1** ktorá sa potom mení v istom bode na **0**.

Zvyčajne sa zapisuje ako počet jednotiek na začiatku.
napr:
/8 -> 1111 1111.0000 0000.0000 0000.0000 0000

## MAC adresa
Nemenná adresa vypálená na sieťovej karte. Identifikuje konkrétne zariadenia. 
Je unikátna.