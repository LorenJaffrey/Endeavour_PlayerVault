---
tags:
  - Regeln/Endeavour/Merkmal/Klasse/Mönch
aliases:
  - Ki-Punkt
  - Ki-Punkte
Einsatz: Passiv
Klasse: "[[Mönch]]"
Stufe: 2
---
# `=this.file.name`
Dein Ki-Maximum entspricht deiner [[Entschlossenheit|EN]].
Du kannst nie mehr [[Ki]] haben als dieses Maximum.

Du erhältst [[Ki]] zurück:
- Bei einer [[Sichere Rast|Sicheren Rast]]: alle Punkte.
- Bei einer [[Feldrast]]: die Hälfte deines Maximums (aufgerundet).
- Beim [[Verschnaufen]]: 1 Punkt.

Du kannst [[Ki|Ki-Punkte]] ausgeben, um die folgenden Aktionen einzusetzen.
Die Kosten stehen bei der jeweiligen Aktion:

```dataview
TABLE WITHOUT ID

file.link AS "Title",
Einsatz

FROM #Regeln/Endeavour/Merkmal/Klasse/Mönch/Ki-Aktion  

SORT file.name
```