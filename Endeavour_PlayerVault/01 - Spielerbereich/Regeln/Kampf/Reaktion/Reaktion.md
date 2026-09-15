---
tags:
  - Regeln/Nimble/Kampf
aliases:
  - Reaktionen
---
# `=this.file.name`
[[Reaktion|Reaktionen]] kosten normalerweise 1 [[Aktionspunkte|Aktionspunkt]] ([[Aktionspunkte|AP]]) und können ausgeführt werden, wenn du **NICHT** am [[Zug]] bist. 
Ein Held kann jede [[Reaktion]] höchstens einmal pro [[Runde]] einsetzen. 
Wie sich das auf den AP-Pool deines nächsten Zuges auswirkt, siehe [[Aktionspunkte#Reaktionen und der AP-Pool zwischen den Zügen]].

```dataview
TABLE WITHOUT ID

file.link AS "Reaktion",
Beschreibung,
Voraussetzung,
Auslöser,
Kosten

FROM #Zug/Reaktion

SORT file.name
```