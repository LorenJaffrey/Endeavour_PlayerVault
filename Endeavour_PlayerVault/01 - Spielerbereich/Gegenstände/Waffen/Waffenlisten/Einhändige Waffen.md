---
tags:
  - Liste/Waffen
---
# `=this.file.name`

```dataview
TABLE WITHOUT ID
file.link AS "Waffe",
"`dice:" + Schaden + "\|none\|noform`"  AS "Schaden",
Schadensart, 
Größe, 
Eigenschaften
FROM #Gegenstand/Waffe/Nahkampfwaffe AND !#Gegenstand/Magischer_Gegenstand 
WHERE Hände < 2
SORT file.name
```