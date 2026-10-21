# `=this.file.name`

```dataview
TABLE WITHOUT ID

file.link AS "Merkmal", Einsatz, Klasse, Stufe, Beschreibung

FROM #Regeln/Endeavour/Merkmal/Klasse

SORT Klasse, Stufe, file.name
```