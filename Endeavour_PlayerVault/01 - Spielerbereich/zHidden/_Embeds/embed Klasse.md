## Eigenschaften

### Kernattribute
`$=dv.list(dv.current().Kernattribute)`

### Rettungswürfe
- [[Vorteil und Nachteil|Vorteil]] auf:
`$=dv.list(dv.current().Rettungswürfe.Vorteil)`
- [[Vorteil und Nachteil|Nachteil]] auf: 
`$=dv.list(dv.current().Rettungswürfe.Nachteil)`

### Trefferpunkte
[[Trefferpunkte|TP]] auf Stufe 1: (`=this.BasisTP` + [[Konstitution]]) x 2
[[Trefferpunkte|TP]] pro Stufenaufstieg: `=this.BasisTP` + [[Konstitution]]

### Resilienzpunkte
[[Resilienzpunkte|RP]] auf Stufe 1: (`=this.BasisRP` + [[Entschlossenheit]]/2 abgerundet) x 2
[[Resilienzpunkte|RP]] pro Stufenaufstieg: `=this.BasisRP` + [[Entschlossenheit]]/2 abgerundet

### Waffen
`$=dv.list(dv.current().Übung.Waffen)`

### Rüstung
`$=dv.list(dv.current().Übung.Rüstungen)`