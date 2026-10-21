---
aliases:
  - Aktion
---
# `=this.file.name`
Jede [[Aktionen|Aktion]] kann höchstens einmal pro [[Zug]] ausgeführt werden.

```dataview
TABLE WITHOUT ID

file.link AS "Aktion",
Beschreibung,
Kosten

FROM #Regeln/Endeavour/Zug/Aktion

SORT file.name
```