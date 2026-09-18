---
aliases:
  - Armbrust
  - Armbrüsten
tags:
  - Liste/Waffen
---
# `=this.file.name`

```dataview
TABLE WITHOUT ID
file.link AS "Waffe",
Range1 AS "MIN-RW", 
Range2 AS "GND-RM", 
Range3 AS "MAX-RW", 
"`dice:" + SchadenFern + "\|none\|noform`"  AS "Schaden",
SchadensartFern AS "Schadensart",
RüstungsdurchschlagFern AS "Rüstungsdurchschlag",
EigenschaftenFern AS "Eigenschaften",
Mindeststärke,
Hände
FROM #Gegenstand/Waffe/Armbrust AND !#Gegenstand/Magischer_Gegenstand
SORT file.name
```