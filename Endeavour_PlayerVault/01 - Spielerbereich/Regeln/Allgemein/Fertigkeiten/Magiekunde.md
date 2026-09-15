---
tags:
  - Regeln/Nimble/Fertigkeit/Verstand
Attribut: "[[Verstand]]"
---
# `=this.file.name`
Abhängiges Attribut: `=this.Attribut`

Situationen in denen man sich an arkanes Wissen erinnern muss.
Beispiele:
- Zaubersprüche
- magische Gegenstände
- mystische Symbole
- magische Schulen
- Ebenen der Existenz und deren Bewohner:

```dataview
TABLE WITHOUT ID

file.link AS "Title",
Identifizieren,
Plündern

FROM #Kreatur/Typ

WHERE contains(Identifizieren, [[Magiekunde]]) OR contains(Plündern, [[Magiekunde]])

SORT Identifizieren, file.name
```