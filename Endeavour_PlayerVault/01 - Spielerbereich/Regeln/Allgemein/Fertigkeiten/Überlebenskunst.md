---
tags:
  - Regeln/Nimble/Fertigkeit/Instinkt
Attribut: "[[Instinkt]]"
---
# `=this.file.name`
Abhängiges Attribut: `=this.Attribut`

Beispiele:
- Spuren lesen
- Wild jagen
- Gruppe durch die vereiste Ödnis führen
- Anzeichen finden ob in der Nähe eine bestimmte Tierart lebt
- Wetter vorhersagen
- natürliche Gefahren wie Treibsand vermeiden
- Nahrung finden

```dataview
TABLE WITHOUT ID

file.link AS "Title",
Identifizieren,
Plündern

FROM #Kreatur/Typ

WHERE contains(Identifizieren, [[Überlebenskunst]]) OR contains(Plündern, [[Überlebenskunst]])

SORT Identifizieren, file.name
```