---
aliases:
  - Stärkewurf
  - Stärkewürfe
  - Stärkewürfen
  - Stärkewurfs
  - ST
  - STR
tags:
  - Regeln/Nimble/Attribut
Beschreibung: Misst die körperliche Kraft, das athletische Training und das Maß in dem du rohe Gewalt ausüben kannst.
---
# `=this.file.name`
`=this.Beschreibung`

[[Stärke]] wird verwendet bei:
- [[Inventar]]
- Schieben, Ziehen, Heben
- [[Stärkerettungswürfe|ST-Rettungswürfen]]

## Verbundene Fertigkeiten
```dataview
TABLE WITHOUT ID

file.link AS "Fertigkeit",
Beschreibung

FROM #Regeln/Nimble/Fertigkeit/Stärke 

SORT file.name
```