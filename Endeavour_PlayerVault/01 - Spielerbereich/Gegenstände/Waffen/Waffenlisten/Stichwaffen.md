---
tags:
  - Liste/Waffen
---
# `=this.file.name`

```dataview
TABLE WITHOUT ID
file.link AS "Waffe",
Reichweite,
"`dice:" + Schaden + "\|none\|noform`"  AS "Schaden",
Schadensart,
Rüstungsdurchschlag AS "RD",
Mindeststärke AS "Min-ST", 
Hände, 
Eigenschaften
FROM #Gegenstand/Waffe/Stichwaffe AND #Gegenstand/Waffe/Nahkampfwaffe AND !#Gegenstand/Magischer_Gegenstand 
SORT größe, file.name
```