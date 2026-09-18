# `=this.file.name`
Jeder Behälter hat zwei Kennzahlen:
  - maximale Anzahl an Plätzen die mit Ausrüstung belegt werden können
  - maximale Gegenstandsgröße die der Behälter aufnehmen kann

```dataview
TABLE WITHOUT ID

file.link AS "Behälter", Plaetze AS "Plätze", MaxGroesse AS "MaxGröße", Kosten

FROM #Gegenstand/Behälter 

SORT file.name
```
