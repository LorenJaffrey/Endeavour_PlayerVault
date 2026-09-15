---
aliases:
  - Aktion
---
# `=this.file.name`

```dataview
TABLE WITHOUT ID

file.link AS "Aktion",
Beschreibung,
Kosten

FROM #Zug/Aktion

SORT file.name
```