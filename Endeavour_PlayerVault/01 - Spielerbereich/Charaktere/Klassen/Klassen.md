---
tags:
  - Regeln/Endeavour
---
# `=this.file.name`

```dataview
TABLE WITHOUT ID

file.link AS "Title",
Kernattribute,
Beschreibung

FROM #Regeln/Endeavour/Charakter/Klasse

SORT file.name
```