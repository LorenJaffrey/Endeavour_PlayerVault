---
tags:
  - Regeln/Nimble/Fertigkeit/Verstand
Attribut: "[[Verstand]]"
---
# `=this.file.name`
Abhängiges Attribut: `=this.Attribut`

Religiöses Wissen.
Beispiele:
- Gottheiten
- Riten
- Gebete
- religiöse Hierarchien
- heilige Symbole
- Praktiken geheimer Kulte
- Wissen über folgende Kreaturen:

```dataview
TABLE WITHOUT ID

file.link AS "Title",
Identifizieren,
Plündern

FROM #Kreatur/Typ

WHERE contains(Identifizieren, [[Religion]]) OR contains(Plündern, [[Religion]])

SORT Identifizieren, file.name
```