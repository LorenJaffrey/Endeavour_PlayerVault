|                            |                                                                                                                       |
| -------------------------- |:---------------------------------------------------------------------------------------------------------------------:|
| [[Verschwinden]]           |                                  `INPUT[toggle:InputData.Fähigkeiten.Verschwinden]`                                   |
| [[Hinterhältiger Angriff (old)]] | `$="```dice:" + dv.page(dv.current().Hintergrund.Klasse).HinterhältigerAngriff["Stufe"+dv.current().Stufe] + "d6```"` |

```dataview
TABLE WITHOUT ID

file.link AS "Raffinierter Schlag",
Kosten

FROM #Merkmal/Klasse/Schurke/Raffinierter_Schlag

WHERE Stufe < 14

SORT file.name
```

#### Apparaturen (max `=ceil(this.Stufe/2)`)
|                  Apparatur 1                  |                  Apparatur 2                  |                  Apparatur 3                  |
|:---------------------------------------------:|:---------------------------------------------:|:---------------------------------------------:|
| `INPUT[toggle:InputData.Apparaturen.Ladung1]` | `INPUT[toggle:InputData.Apparaturen.Ladung2]` | `INPUT[toggle:InputData.Apparaturen.Ladung3]` |


```dataview
TABLE WITHOUT ID
file.link AS "Apparaturen", 
SG,
Einsatz
FROM #Merkmal/Klasse/Schurke/Meistertüftler/Apparatur 
WHERE contains(this.Niptac.Apparaturen, file.link)
SORT SG, file.link
```

|                                                               |                                                                                                         |
| ------------------------------------------------------------- |:-------------------------------------------------------------------------------------------------------:|
| [[Mechanische Apparaturen#Tüftlerwurf\|Tüftlerwurf]]          | `="```dice: 1d20 + " + ((ceil(this.Stufe/4)+1) + (floor(((this.Attribute.Intelligenz)-10)/2))) + "```"` |
| [[Mechanische Apparaturen#Apparatur-SG\|Gegner-Rettungswurf]] |              `= 8 + (ceil(this.Stufe/4)+1) + (floor(((this.Attribute.Intelligenz)-10)/2))`              |
