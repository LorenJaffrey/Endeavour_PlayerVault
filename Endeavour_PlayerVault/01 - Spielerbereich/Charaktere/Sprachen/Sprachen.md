---
tags:
  - Regeln/Endeavour
aliases:
  - Sprache
---
# `=this.file.name`
## Standardsprachen
```dataview
TABLE WITHOUT ID

file.link AS "Sprache", 
Ursprung, 
Schrift

FROM #Sprache/Standard 

SORT file.name
```

## Exotische Sprachen
```dataview
TABLE WITHOUT ID

file.link AS "Sprache", 
Ursprung, 
Schrift

FROM #Sprache/Selten 

SORT file.name
```

## Sonstige Sprachen
```dataview
TABLE WITHOUT ID

file.link AS "Sprache", 
Ursprung

FROM #Sprache/Sonstige 

SORT file.name
```