# 1
![[uloha1-PS.excalidraw]]

# 2
Ťahák:
(Magic number -> počet sietí)
![[uloha2 - PS.excalidraw]]

Počítanie masky:

Dĺžka masky|Magické číslo|Oktét
---|---|---
/27|32|4
/30|4|4
/19|32|3
/16|1|2
/13|8|2
/7|2|1
/22|4|3

# 3

Máme sieť 192.168.0/22. Rozdeľte túto sieť na 7 rovnako veľkých podsietí.Zapíšte ich broadcastové adresy:
![[uloha3 - PS.excalidraw]]

Názov podsiete|Sieťová adresa|Broadcast-ová adresa
---|---|---
L1|192.168.0.0|192.168.0.127
L2|192.168.0.128|192.168.0.255
L3|192.168.1.0|192.168.1.127
L4|192.168.1.128|192.168.1.255
L5|192.168.2.0|192.168.2.127
L6|192.168.2.128|192.168.2.255
L7|192.168.3.0|192.168.3.127

# 4
## A
Majme sieť 192.168.0.0/18 rozdeľme ju na 4 rovnako veľké podsiete. Zapíšte sieťovú adresu a dĺžku masky:
![[uloha4a - PS.excalidraw]]

192.168.0.0/20|192.168.16.0/20|192.168.32.0/20|192.168.48.0/20
---|---|---|---

## B
Rozdeľte tretiu v poradí (v [[#A]]) na 5 rovnako veľkých častí a zapíšte sieťovú a dĺžky prvých dvoch:
![[uloha4b - PS.excalidraw]]

192.168.32.0/23|192.168.34.0/23
---|---

## C
V poradí druhú vytvorenú podsieť (v [[#C]]) rozdeľte na 4 rovnako veľké podsiete a zapíšte ich:
![[uloha4c - PS.excalidraw]]

192.168.34.0/25|192.168.34.128/25|192.168.35.0/25|192.168.35.128/25
---|---|---|---

# Písomka 1
Administrátor má k dispozícii nasledujúcu kombináciu IP/MASK:
**147.232.76.255/19**

## 1
Určte o akú adresu sa jedná [Adresa/Použiteľná adresa/Broadcastová adresa]:

Adresa siete -> nemôže byť, IP je nepárna

![[pisomka1 - PS.excalidraw]]
Je to **použiteľná adresa**.

## 2
Napíšte sieťovú a broadcastovú adresu:
**Sieťová: 147.232.64.0**
**Broadcast: 147.232.95.255**

## 3
Rozdeľte na 4 rovnako veľké časti a zapíšte sieťové adresy

![[pisomka3 - PS.excalidraw]]

147.232.64.0/21|147.232.72.0/21|147.232.80.0/21|147.232.88.0/21
---|---|---|---

## 4
Druhú v poradí z vytvorených podsietí v 3 rozdeľte na polovicu a zapíšte sieťovú adresu v poradí druhej vytvorenej:

![[pisomka4 - PS.excalidraw]]

**147.232.76.0/22**

## 5
Prvú podsieť ďalej podsieťuje podľa nasledujúcich špecifikácií, čo sa týka poćtu použiteľných adries:

**L1** : 200
**L2** : 400
**L3** : 64
**L4** : 50
**L5** : 24
**L6** : 147.232.74.16/28

![[pisomka5 - PS.excalidraw]]

## 6
Napíšte o **L3**:

Sieťová adresa: **147.232.74.128**
Prvá použiteľná: **147.232.74.129**
Posledná použiteľná: **147.232.75.254**
Broadcastová: **147.232.75.255**
Maska: **255.255.255.128**
Počet adries: **128**
Počet použiteľných adries: **126**

# Písomka 2
## 1
Máme k dispozícii:
**47.214.119.0/22**

![[pisomka-2_1 - PS.excalidraw]]

Jedná sa o:
**Použiteľnú adresu**

## 2
Napíšte:

Sieť: **47.214.116.0**
Broadcast: **47.214.119.255**

## 3
Rozdeľte na čo najefektívnejšie:
![[pisomka-2_2 - PS.excalidraw]]

## 4
Napíšte o L1 podsieti:
Sieťová adresa: **47.214.116.0**
Prvá použiteľná: **47.214.116.1**
Posledná použiteľná: **47.214.117.254**
Broadcastová: **47.214.117.255**
Maska: **255.255.192.0** /23
Počet adries: **512**
Počet použiteľných adries: **510**