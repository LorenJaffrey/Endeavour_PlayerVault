<br />

```dynamic-embed
[[embed Character Sheet Healthbar]]
```

```dynamic-embed
[[embed Character Sheet Magicbar]]
```

<br />

> [!caution | bg-c-plain c-custom-lightblue]+ Hintergrund
> |                                                              |                               |
> | ------------------------------------------------------------ | ----------------------------- |
> | Stufe                                                        | `INPUT[number:Stufe]`         |
> | [[Spezies]]                                                  | `=this.Hintergrund.Volk`      |
> | [[Klassen DnD\|Klasse]]                                          | `=this.Hintergrund.Klasse`    |
> | `$=dv.page(dv.current().Hintergrund.Klasse).Name_Subklassen` | `=this.Hintergrund.Subklasse` |
> | [[Gesinnung]]                                                | `=this.Hintergrund.Gesinnung` |
> | [[Herkunft]]                                                 | `=this.Hintergrund.Herkunft`  |

<br />

> [!info | bg-c-plain]- Aussehen
> |                 |                                  |
> | --------------- | -------------------------------- |
> | Geschlecht      | `=this.Aussehen.Geschlecht`      |
> | Alter           | `=this.Aussehen.Alter`           |
> | Größenkategorie | `=this.Aussehen.Größenkategorie` |
> | Größe           | `=this.Aussehen.Größe`           |
> | Gewicht         | `=this.Aussehen.Gewicht`         |
> | Augenfarbe      | `=this.Aussehen.Augenfarbe`      |
> | Haarfarbe       | `=this.Aussehen.Haarfarbe`       |
> | Hautfarbe       | `=this.Aussehen.Hautfarbe`       |

<br />

> [!info | bg-c-plain]- Persönlichkeitsmerkmale 
> `=this.Persönlichkeit.Persönlichkeitsmerkmale[0]`
> `=this.Persönlichkeit.Persönlichkeitsmerkmale[1]`
> `=this.Persönlichkeit.Persönlichkeitsmerkmale[2]`

<br />

> [!info | bg-c-plain]- Ideale
> `=this.Persönlichkeit.Ideale`

<br />

> [!info | bg-c-plain]- Bindungen
> `=this.Persönlichkeit.Bindungen`

<br />

> [!info | bg-c-plain]- Makel
> `=this.Persönlichkeit.Makel`