## Kernattribute
`$=dv.list(dv.current().Kernattribute)`

## Trefferpunkte
[[Trefferwürfel]]: 1`="W" + this.Trefferwürfel` pro Stufe
[[Trefferpunkte]] auf Stufe 1: `=this.Trefferwürfel` + [[Konstitution]]
[[Trefferpunkte]] pro Stufenaufstieg: `$="```dice:1d" + dv.current().Trefferwürfel + "```"` (min. `=this.Trefferwürfel/2`) + [[Konstitution]]

## Waffen
`$=dv.list(dv.current().Übung.Waffen)`

## Rüstung
`$=dv.list(dv.current().Übung.Rüstungen)`

## Rettungswürfe
- [[Vorteil und Nachteil|Vorteil]] auf **EINEN** der folgenden:
`$=dv.list(dv.current().Rettungswürfe.Vorteil)`
- [[Vorteil und Nachteil|Nachteil]] auf **EINEN** der folgenden: 
`$=dv.list(dv.current().Rettungswürfe.Nachteil)`