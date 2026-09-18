# `=this.file.name`

```dataview
TABLE WITHOUT ID
file.link AS "Waffe",
Plaetze AS "Plätze",
Stapelgroesse AS "Stapelgröße",
Kosten, 
Verfügbarkeit
FROM #Gegenstand/Waffe AND !#Gegenstand/Magischer_Gegenstand
```