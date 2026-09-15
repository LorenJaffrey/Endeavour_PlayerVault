---
aliases:
  - Zustand
---
# `=this.file.name`
Zustände ändern die Fähigkeiten einer Kreatur auf verschiedene Arten und können die Folge von Zaubern, Klassenmerkmalen, Monsterangriffen oder anderen Effekten sein. 
Die meisten Zustände, wie [[Blind]], beschreiben Einschränkungen, aber einige, wie [[Unsichtbar]], können nützlich sein. 
Ein [[Zustände|Zustand]] hält entweder an, bis er aufgehoben wird (der Zustand liegend beispielsweise endet, indem du aufstehst), oder für eine Wirkungsdauer, die durch seinen Auslöser bestimmt wird.
Wenn mehrere Effekte einer Kreatur den gleichen Zustand auferlegen, besitzt jede Version des Zustands ihre eigene Wirkungsdauer, doch werden die Auswirkungen des Zustands nicht schlimmer. 
Eine Kreatur hat einen Zustand entweder oder hat ihn nicht. 
Die folgenden Beschreibungen legen fest, was passiert, wenn eine Kreatur einen Zustand erhält.

```dataview
TABLE WITHOUT ID
file.link AS "Title"
FROM #Zustand
SORT file.name
```

## Zustandsimmunität
Eine Kreatur die immun gegen einen bestimmten Zustand ist, bleibt von den Auswirkungen des Zustand unbeeinflusst.

## Zustandsresistenz
Wenn ein Effekt dich mit diesem [[Zustand]] belegen würde, machst du den dafür vorgesehenen [[Rettungswurf]] mit [[Vorteil und Nachteil|Vorteil]]. 