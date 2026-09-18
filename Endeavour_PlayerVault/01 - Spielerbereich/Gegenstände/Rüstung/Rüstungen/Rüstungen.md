---
aliases:
  - Rüstung
---
# `=this.file.name`

```dataview
TABLE  WITHOUT ID 
file.link AS "Title",
Klasse, 
RK, 
BW_cap AS "BW Cap",
Heimlichkeit, 
Stärke, 
Eigenschaften, 
Gewicht, 
Kosten
FROM #Gegenstand/Rüstung
SORT Klasse, RK, BW_cap
WHERE file.name != "Vorlage Rüstung"
AND Klasse
```