***********
Algebraická sémantika je založená na **abstraktných algebrách**.
Tieto algebry sú objekty, reprezentujú **typ** a **operácie** nad nimi.

Táto sémantika špecifikuje **Abstraktné dátové typy** (ADT), ktorých konkrétna reprezentácia už nie je súčasťou špecifikácie.

Výhody:
- **utajenie informácie** vďaka nešpecifikácie ADT
- **zaúzdrenie** - všetky informácie, ktoré potrebujeme o type vedieť sú v jednej štruktúre
- **generické typy** - je možné použiť jeden ADT na tvorbu ďalších inštancií (ako vzor, či šablónu), napr. $Int$ a $Nat$.

# Algebraická špecifikácia
Na špecifikáciu ADT najprv potrebujeme  **mnohodruhovú signatúru**:
$$
\Sigma = (S,O)
$$
, kde:
- $S$ je množina druhov a názvov typu
- $O$ je množina operačných symbolov a ich názvov

**Algebraickú špecifikáciu** teda berieme ako dvojicu:
$$
Spec = (\Sigma, Eq)
$$
, kde $Eq$ je množina algebraických axióm v tvare rovnosti.

Axiómy popisujú logické vlastnosti operačných symbolov. Nakoľko sú v rovnosti označuje sa táto logika ako **ekvacionálna**.

# Sémantika
Nakoľko [[#Algebraická špecifikácia|algebraická špecifikácia]] pracuje len so syntaxou potrebujeme aj ďalší systém, ktorý bude vedieť pracovať s jej sémantikou.

**Algebraická sémantika** je definovaná ako **mnohodruhová algebra** nad signatúrou a slúži ako model pre špecifikáciou.

**Mnohodruhová $\Sigma$-algebra**:
$$
A = (S^A,O^A)
$$
, kde:
- $S^A$ je trieda reprezentacií druhov zo signatúry $\Sigma$
- $O^A$ je trieda skutočných operácií nad príslušnými druhmi zo signatúry
pričom $S^A = \{S^A_i | i=1...n\}$ 

Množiny $S^A_i$ sa zvyknú nazývať aj **nosné množiny algebry** (carrier sets).




---