---
tags:
  - Regeln/Endeavour
---
# `=this.file.name`

```dataview
TABLE WITHOUT ID

file.link AS "Title",
Kernattribute,
BasisTP AS "TP",
BasisRP AS "RP",
Beschreibung

FROM #Regeln/Endeavour/Charakter/Klasse

SORT file.name
```