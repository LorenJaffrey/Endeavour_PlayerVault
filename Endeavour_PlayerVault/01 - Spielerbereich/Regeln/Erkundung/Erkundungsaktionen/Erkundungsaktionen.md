---
tags:
  - Regeln/Nimble
aliases:
  - Erkundungsaktion
---
# `=this.file.name`
Während jeder [[Erkundungsrunde]] wählt jeder Charakter eine [[Erkundungsaktionen|Erkundungsaktion]]. 
Es ist völlig normal, dass mehrere oder alle Charaktere dieselbe [[Erkundungsaktionen|Erkundungsaktion]] wählen, zum Beispiel wenn die ganze Gruppe gemeinsam einen Korridor entlang geht.

```dataview
TABLE WITHOUT ID
file.link AS "Erkundungsaktion",
Beschreibung
FROM #Erkundung/Aktion
SORT file.name
```

Eine Kreatur, die statt einer eigenen [[Erkundungsaktionen|Erkundungsaktion]] einem anderen Charakter hilft, folgt den Regeln zur [[Attribute#Zusammenarbeit|Zusammenarbeit]].