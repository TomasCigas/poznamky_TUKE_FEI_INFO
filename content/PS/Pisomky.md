# 7.4
## Prepojenie zariadení – použitie káblov 
- **konzolový kábel** -> slúži na konfigurovanie zariadení
- **priamy kábel** -> slúži na výmenu dát medzi zariadeniami, ktoré nie sú na rovnakej úrovni (OSI)
- **krížený kábel** -> slúži na výmenu dát medzi zariadeniami, ktoré sú na rovnakej úrovni
- **seriálový kábel** -> prepojenue sériovýc rozhraní na routry

## Režimy IOS (Používateľský režim...)  
- **používateľský režim** -> základný režim na zariadení, poskytuje obmedzené služby a informácie, na ďalší sa dostaneme príkazom *enable*
- **privilegovaný režim** -> poskytuje viac služieb ako používateľský režim, obsahuje citlivé informácie o zariadení, zvyčajne je prístup k nemu zaheslovaný, pokračuje sa *configure terminal*
- **globálny konfiguračný režim** -> poskytuje služby na konfigurovanie zariadenia, nad ním sa nachádzajú ešte *špeciálne konfiguračné režimi*, ktoré slúžia na bližšie konfigurácie

## Príkazy na nastavenie hesla do privilegovaného režimu a ich rozdiel  
enable:
- **password** heslo -> zahesluje sa, ale do running-config sa zapíše ako normálny text
- **secret** heslo -> zahesluje sa, a zapíše sa zašifrovaná verzia

- existuje príkaz **service password-encryption**, pomocou ktorého môžeme zašifrovať jednoduchou šifrou heslá v running config

## Rozdiel medzi telnet a SSH  
**Telnet** -> jednoduchý TCP-IP protokol na prístup k zariadeniu
**SSH** -> Secure Shell zašifrovaný prístup k zariadeniu

## Čo je všetko potrebné pre nastavenie SSH  



## Na čo slúži príkaz service password-encryption  

## Rozdiel medzi Classfull a Classless podsietovaním  

## Manažmentová vlan (na čo slúži, ako sa konfiguruje)  

## Na čo slúži predvolená brána  

## Na čo slúži CDP  

## Na čo slúži mód access a trunk  

## Čo sú VLAN a na čo slúžia  

## Čo je to natívna VLAN  

## Na čo slúži link local adresa v ipv6  

## Módy narušenia pri port security (aké sú a čo robia)  

## Čo znamená full a half duplex  

## Na čo slúži mdix  

## Na čo slúži príkaz switchport port-security mac-address sticky  

## Na čo slúži metóda router on a stick  

## Ako sa konfiguruje router on a stick