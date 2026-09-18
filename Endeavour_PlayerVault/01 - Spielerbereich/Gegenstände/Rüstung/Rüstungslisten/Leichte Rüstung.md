---
aliases: 
  - Leichter Rüstung
tags:
  - Gegenstand/Rüstung
---
# `=this.file.name`

```dataview
TABLE  WITHOUT ID 
file.link AS "Title",
Klasse, 
RK, 
Stärke, 
BW_cap AS "BW Cap", 
Heimlichkeit,
Eigenschaften, 
Gewicht, 
Kosten
FROM #Gegenstand/Rüstung/Leicht
SORT RK
```