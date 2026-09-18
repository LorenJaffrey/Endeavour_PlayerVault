---
aliases:
  - Einfache Waffe
  - Einfachen Waffe
  - Einfachen Waffen
tags:
  - Liste/Waffen
---
# `=this.file.name`

## Nahkampfwaffen
```dataview
TABLE WITHOUT ID
file.link AS "Waffe",
Reichweite,
"`dice:" + Schaden + "\|none\|noform`"  AS "Schaden",
Schadensart,
Rüstungsdurchschlag AS "RD",
Mindeststärke AS "Min-ST",
Hände,
Größe,
Eigenschaften
FROM #Gegenstand/Waffe/Einfach AND #Gegenstand/Waffe/Nahkampfwaffe AND !#Gegenstand/Magischer_Gegenstand
SORT file.name
```

## Fernkampfwaffen
```dataview
TABLE WITHOUT ID
file.link AS "Waffe",
"`dice:" + SchadenFern + "\|none\|noform`"  AS "Schaden",
SchadensartFern AS "Schadensart",
RüstungsdurchschlagFern AS "RD",
Range1 AS "Min RW",
Range2 AS "Gnd RW",
Range3 AS "Max RW",
Mindeststärke AS "Min-ST",
Hände,
Größe,
EigenschaftenFern AS "Eigenschaften"
FROM #Gegenstand/Waffe/Einfach AND #Gegenstand/Waffe/Fernkampfwaffe AND !#Gegenstand/Magischer_Gegenstand
SORT file.name
```
