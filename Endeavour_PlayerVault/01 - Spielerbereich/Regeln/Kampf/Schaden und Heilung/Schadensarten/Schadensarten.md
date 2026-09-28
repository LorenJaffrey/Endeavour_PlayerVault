---
tags: 
  - Regeln/Endeavour/Schaden
aliases:
  - Schadensart
---
# `=this.file.name`

```dataview
TABLE WITHOUT ID

file.link AS "Schadensart",
Kategorie

FROM #Regeln/Endeavour/Schaden/Schadensart

WHERE Kategorie

SORT Kategorie, file.name
```