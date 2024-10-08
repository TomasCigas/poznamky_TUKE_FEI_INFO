# Model ISO/OSI
**Vrstvy**:
![[ISO-TCP.excalidraw]]

## Fyzická vrstva
Fyzicé a elektrické špecifikácie zariadení.
Umožňuje prenos dát, ktorým však nerozumie.

Na fyzickej vrstve pracujú **HUB**-y a **opakovače**.
**Opakovač** -> zosilňuje vstup a posiela ho na výstup
**HUB** -> Umožňuje prepájanie viacerých počítačov, pri čom môžu komunikovať len 2 "uzly" naraz (nepoužíva sa)

Dátová jednotka (PDU): **Bity**

Bližšie: [[Sieťové médiá]]

## Linková vrstva
Linková vrstva poskytuje funkcionalitu a prostriedky na prenos dát medzi dvoma systémami.
Poskytuje detekciu/opravu chýb

V minulosti sa využíval **Bridge** -> Dokáže čítať dáta. Bridge blokuje alebo prepúšťa dáta prichádzajúce z HUB-u na základe [[Adresácia#MAC adresa|MAC adresy]], ktoré sa naučil pasívnym počúvaním.

Dnes sa využíva **Switch** -> Zariadenie, ktoré spája v rámci lokálnej siete počítače na základe MAC adresy. Rozdiel medzi HUB-om je, že segmentujeme komunikáciu a môže prebiehať komunikácia na viacerých PC naráz.

Dátová jednotka (PDU): **Rámce**

### LLC vrstva
Komunikuje so sieťovou vrstvou.
Určuje protokol sieťovej vrstvy pre rámec.
Zjednocuje viacerým L3 protokolom (IPv4/IPv6) prístup k sieti.

### MAC vrstva
Definuje procesy pre prístup k médiu vykonávané HW.
#add_info 

## Sieťová vrstva
**Sieťová vrstva** as stará o smerovanie a kontrolu dát, taktiež aj ako (de)segmentáciu a kontrolu chýb

Využíva sa tu **Router** -> preposiela dáta na základe [[Adresácia#IP adresa|IP adresy]]

Dátová jednotka (PDU): **Pakety**

## Transportná vrstva
**Transportná vrstva** má na starosti spoľahlivosť daného spojenia

Využívajú sa:
[[TCP a UDP|TCP]] (Transmission Control Protocol)
[[TCP a UDP|UDP]] (User Datagram Protocol)

**Sledovanie informácii**:
**Segmntácia**:
**daco**:
#add_info 

**Port** -> 

Dátová jednotka (PDU): **Segmenty**

## Relačná vrstva
**Relačná vrstva** poskytuje mechanizmus správy dialógi medzi aplikačnými procesmi koncového používateľa.

Táto vrstva vytvára, udržiava a ukončuje spojenia (sessions).

Dátová jednotka (PDU): **Dáta**

## Prezentačná vrstva
Funkciou **prezentačnej vrstvy** je transformovať do tvaru, ktorý používajú aplikácie (šifrovanie, konverzia, kompresia a i.)

Dátová jednotka (PDU): **Dáta**

## Aplikačná vrstva
**Aplikačná vrstva** implementuje rozhranie pre aplikačné procesy a poskytuje im služby

Dátová jednotka (PDU): **Dáta**

## Média L1 vrstvy
Elektrické signály -> metalické káble

# Model TCP/IP



