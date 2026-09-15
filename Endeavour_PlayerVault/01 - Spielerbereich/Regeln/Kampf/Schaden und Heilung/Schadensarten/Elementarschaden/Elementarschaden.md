---
tags:
  - Regeln/Nimble/Schaden/Schadensart/Elementar
---
# `=this.file.name`
[[Elementarschaden]] ist Schaden, der durch natürliche oder stoffliche Kräfte wie Feuer, Kälte, Blitz, Säure oder Gift entsteht.
Er wird normalerweise durch Umwelteinflüsse, alchemistische Substanzen, elementare Waffenwirkungen oder elementare Magie verursacht.

```dataview
TABLE WITHOUT ID

file.link AS "Schadensart"

FROM #Regeln/Nimble/Schaden/Schadensart/Elementar

WHERE Kategorie

SORT file.name
```