---
tags:
  - Regeln/Nimble/Schaden/Schadensart/Physisch
---
# `=this.file.name`
[[Physischer Schaden]] ist Schaden, der direkt auf den Körper eines Ziels einwirkt und durch Waffen, Stöße, Schnitte, Einstiche, Aufprall oder andere körperliche Einwirkungen verursacht wird. 
Er umfasst alle Schadensarten, die aus direkter körperlicher Gewalt entstehen.

```dataview
TABLE WITHOUT ID

file.link AS "Schadensart"

FROM #Regeln/Nimble/Schaden/Schadensart/Physisch

WHERE Kategorie

SORT file.name
```