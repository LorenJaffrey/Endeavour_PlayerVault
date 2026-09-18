# `=this.file.name`

## Bier
```dataview
TABLE WITHOUT ID

file.link AS "Getränk", Art, Kosten

FROM #Gegenstand/Nahrungsmittel/Getränk/Bier

SORT file.name
```

## Wein
```dataview
TABLE WITHOUT ID

file.link AS "Getränk", Art, Kosten

FROM #Gegenstand/Nahrungsmittel/Getränk/Wein

SORT file.name
```

## Spirituosen
```dataview
TABLE WITHOUT ID

file.link AS "Getränk", Art, Kosten

FROM #Gegenstand/Nahrungsmittel/Getränk/Spirituosen

SORT file.name
```

## Sonstiges
```dataview
TABLE WITHOUT ID

file.link AS "Getränk", Art, Kosten

FROM #Gegenstand/Nahrungsmittel/Getränk AND -#Gegenstand/Nahrungsmittel/Getränk/Bier AND -#Gegenstand/Nahrungsmittel/Getränk/Wein AND -#Gegenstand/Nahrungsmittel/Getränk/Spirituosen

SORT file.name
```
