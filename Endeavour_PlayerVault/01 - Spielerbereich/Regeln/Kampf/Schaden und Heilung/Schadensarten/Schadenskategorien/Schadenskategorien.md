---
tags:
  - Regeln/Nimble/Schaden
aliases:
  - Schadenskategorie
---
# `=this.file.name`
Schadenskategorien fassen mehrere einzelne [[Schadensarten]] zu größeren Gruppen zusammen. 
Sie dienen dazu, Widerstände, Effekte und Quellen einfacher zu ordnen und auf einen Blick zu erkennen, ob ein Angriff vor allem körperlich, elementar oder magisch wirkt.

```dataview
TABLE WITHOUT ID

file.link AS "Schadenskategorie"

FROM #Regeln/Nimble/Schaden/Schadensart

WHERE !Kategorie

SORT file.name
```