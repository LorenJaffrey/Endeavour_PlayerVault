---
tags:
  - Regeln/Nimble/Fertigkeit/Verstand
Attribut: "[[Verstand]]"
---
# `=this.file.name`
Abhängiges Attribut: `=this.Attribut`

Situationen in denen man sich an historische Ereignisse erinnern muss.
Beispiele:
- sagenumwobene Personen
- alte Königreiche
- vergangene Kriege
- abgesetzte Dispoten
- verschollene Zivilisationen
- Wissen über sagenumwobene Kreaturen und Humanoide:

```dataview
TABLE WITHOUT ID

file.link AS "Title",
Identifizieren,
Plündern

FROM #Kreatur/Typ

WHERE contains(Identifizieren, [[Geschichte]]) OR contains(Plündern, [[Geschichte]])

SORT Identifizieren, file.name
```