# Entitno-Relačný model
Je to [[Databázové systémy#Údajový model|konceptuálny údajový model]].

**Entita** -> existujúci objekt, rozlíšiteľný od ostatných objektov
**Entitná množina** -> množina entít rovnakého *atribútu*
**Atribút** -> vlastnosť typu entít
**Doména** -> množina povolených hodnôt ( limit atribútu )
**Vzťah**/relácia -> vzťah medzi entitami
**Vzťahová množina** -> matematická [[Množiny a množinové relácie|relácia]], *atribút* môže patriť aj vzťahovej množine

## Chen-ová notácia
ERD je grafický nástroj pre zápis [[#Entitno-relačný model|ER]] modelov

Základné stavebné bloky:
![[stavebne_bloky_chen.excalidraw]]

### Stupeň vzťahu
Počet zúčastnených množín
!! Tieto nie sú Chen ale IES !!
**Unárny**:
![[chen-unarny.excalidraw]]
**Binárny**:
![[chen-binarny.excalidraw]]
**Ternárny**:
![[chen-ternarny.excalidraw]]
**n-árny** -> zriedkavý

### Kardinalita vzťahu
![[chen-kardinalita.excalidraw]]

### Povinnosť/Voliteľnosť vzťahu
Špecifikuje, či existencia entity závisí od existencie inej entity.
- **Totálna** -> ku každému výskytu jednej entity musí existovať výskyt druhej
- **Čiastočná** -> -//- môže ale nemusí

### Slabá entitná množina
Sama nemá vlastný primárny kľúč, identifikuje ju iná (silná) entitná množina.
- **Diskriminátor** -> tzv. čiastočný kľúč, slúži na odlíšenie slabých entít patriacej jednej silnej entite
- **Primárny kľúč** takýchto množín je kombinácia primárneho kľúča silnej entity a diskriminátora tej slabej
Príklad:
![[budova-slaba_entita.excalidraw]]
