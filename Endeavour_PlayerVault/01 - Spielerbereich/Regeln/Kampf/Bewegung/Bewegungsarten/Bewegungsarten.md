---
tags:
  - Regeln/Endeavour
---
# `=this.file.name`
Bestimmte Bewegungsarten haben eine Auswirkung auf die [[Bewegungsrate]].
```dataview
TABLE WITHOUT ID
file.link AS "Bewegungsart"
FROM #Regeln/Endeavour/Bewegung
SORT file.name
```