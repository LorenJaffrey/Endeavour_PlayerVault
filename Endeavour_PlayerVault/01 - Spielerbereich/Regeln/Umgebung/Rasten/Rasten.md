---
tags:
  - Regeln/Nimble/Rasten
aliases:
  - Rast
---
# `=this.file.name`
**Rasten** sind Phasen der Erholung zwischen zwei Abschnitten des Abenteuers. 
Sie dienen dazu, Kraft zu sammeln, Vorräte zu sichern, Wunden zu versorgen und die Gruppe auf die nächsten Gefahren vorzubereiten. 
Je nach Art der Rast ist die Erholung kürzer oder umfassender, und nicht jede Rast setzt die gleichen Bedingungen voraus.

```dataview
TABLE WITHOUT ID

file.link AS "Rast",
Dauer

FROM #Regeln/Nimble/Rasten/Rast  

SORT Dauer, file.name
```