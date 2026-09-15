---
tags: 
  - Regeln/Nimble/Schaden
aliases:
  - Schadensart
---
# `=this.file.name`

```dataview
TABLE WITHOUT ID

file.link AS "Schadensart",
Kategorie

FROM #Regeln/Nimble/Schaden/Schadensart

WHERE Kategorie

SORT Kategorie, file.name
```