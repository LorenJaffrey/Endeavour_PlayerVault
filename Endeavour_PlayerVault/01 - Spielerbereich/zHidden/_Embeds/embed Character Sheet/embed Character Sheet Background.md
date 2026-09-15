<br />

```dynamic-embed
[[embed Character Sheet Healthbar]]
```

## Hintergrund
|                                                              |                               |
| ------------------------------------------------------------ | ----------------------------- |
| Stufe                                                        | `INPUT[number:Stufe]`         |
| [[Spezies]]                                                  | `=this.Hintergrund.Volk`      |
| [[Klassen DnD\|Klasse]]                                          | `=this.Hintergrund.Klasse`    |
| `$=dv.page(dv.current().Hintergrund.Klasse).Name_Subklassen` | `=this.Hintergrund.Subklasse` |
| [[Gesinnung]]                                                | `=this.Hintergrund.Gesinnung` |
| [[Herkunft]]                                                 | `=this.Hintergrund.Herkunft`  |
 
## Aussehen
|                 |                                  |
| --------------- | -------------------------------- |
| Geschlecht      | `=this.Aussehen.Geschlecht`      |
| Alter           | `=this.Aussehen.Alter`           |
| Größenkategorie | `=this.Aussehen.Größenkategorie` |
| Größe           | `=this.Aussehen.Größe`           |
| Gewicht         | `=this.Aussehen.Gewicht`         |
| Augenfarbe      | `=this.Aussehen.Augenfarbe`      |
| Haarfarbe       | `=this.Aussehen.Haarfarbe`       |
| Hautfarbe       | `=this.Aussehen.Hautfarbe`       |

### Persönlichkeitsmerkmale 
`=this.Persönlichkeit.Persönlichkeitsmerkmale[0]`
`=this.Persönlichkeit.Persönlichkeitsmerkmale[1]`
`=this.Persönlichkeit.Persönlichkeitsmerkmale[2]`

### Ideale
`=this.Persönlichkeit.Ideale`

### Bindungen
`=this.Persönlichkeit.Bindungen`
 
### Makel
`=this.Persönlichkeit.Makel`