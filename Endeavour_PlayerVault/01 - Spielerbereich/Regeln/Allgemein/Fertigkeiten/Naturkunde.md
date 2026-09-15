---
tags:
  - Regeln/Nimble/Fertigkeit/Verstand
Attribut: "[[Verstand]]"
---
# `=this.file.name`
Abhängiges Attribut: `=this.Attribut`

Erinnern an natürlich Ereignisse oder Abläufe.
Beispiele:
- bestimmtes Terrain
- Wetter
- natürliche Ereignisse
- Wissen über folgende Kreaturen: 

```dataview
TABLE WITHOUT ID

file.link AS "Title",
Identifizieren,
Plündern

FROM #Kreatur/Typ

WHERE contains(Identifizieren, [[Naturkunde]]) OR contains(Plündern, [[Naturkunde]])

SORT Identifizieren, file.name
```