---
aliases:
  - Information
---
# `=this.file.name`

```dataview
TABLE WITHOUT ID

file.link AS "Information",
SG AS "Schwierigkeitsgrad",
Beschreibung

FROM #Erkundung/Information 

SORT SG ASC
```