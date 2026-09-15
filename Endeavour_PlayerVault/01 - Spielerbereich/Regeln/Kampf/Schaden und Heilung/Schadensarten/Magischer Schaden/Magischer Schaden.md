---
tags:
  - Regeln/Nimble/Schaden/Schadensart/Magisch
---
# `=this.file.name`
[[Magischer Schaden]] ist Schaden, der aus übernatürlicher Energie oder einer bewussten magischen Wirkung hervorgeht und nicht rein körperlich oder elementar ist.
Er wird typischerweise durch Zauber, verfluchte Kräfte, rohe arkane Entladungen, Schattenmagie oder göttlich-gleißende Energie verursacht.

```dataview
TABLE WITHOUT ID

file.link AS "Schadensart"

FROM #Regeln/Nimble/Schaden/Schadensart/Magisch

WHERE Kategorie

SORT file.name
```