---
tags:
  - Regeln/Endeavour
aliases:
  - Fertigkeit
---
# `=this.file.name`
Jede Fertigkeit hat ein zugeordnetes [[Attribute|Attribut]], dessen [[Attribute|Attributswert]] für einen [[Fertigkeiten#Fertigkeitswurf]] herangezogen wird. 
Ein [[Fertigkeiten#Fertigkeitswurf]] stellt eine konkretere Art von [[Attribute#Attributswurf]] dar und profitiert von einem eventuellen Bonus des Anwenders in dieser Fertigkeit.

```dataview
TABLE WITHOUT ID
file.link AS "Fertigkeit",
Attribut
FROM #Regeln/Nimble/Fertigkeit
SORT Attribut, file.name
```

## Fertigkeitswurf
>[!info]
>W20 + [[Attribute|Attributswert]] + [[Fertigkeiten|Fertigkeitswert]] + Bonus/Malus

Für [[Fertigkeiten#Fertigkeitswurf|Fertigkeitswürfe]] gelten ansonsten die selben Regeln wie für [[Attribute#Attributswurf|Attributswürfe]].

## Maximaler Fertigkeitsbonus
Der maximale Bonus einer [[Fertigkeiten|Fertigkeit]] beträgt +10.