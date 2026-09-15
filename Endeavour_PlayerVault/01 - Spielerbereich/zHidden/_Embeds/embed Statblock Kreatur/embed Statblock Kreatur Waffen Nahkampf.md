```dataview
TABLE WITHOUT ID 
file.link AS "Waffe",
Reichweite,
"`dice:1d20+" + (floor(((choice(contains(Eigenschaften, [[Finesse]]), this.Attribute.Geschicklichkeit, this.Attribute.Stärke))-10)/2)+ceil(this.Herausforderungsgrad/4)+1) + "|none|noform`" AS "Angriff",
"`dice:" + Schaden + "+"+floor(((choice(contains(Eigenschaften, [[Finesse]]), this.Attribute.Geschicklichkeit, this.Attribute.Stärke))-10)/2) + "\|none\|noform`"  AS "Schaden",
Schadensart,
Eigenschaften
FROM #Gegenstand/Waffe/Klasse/Nahkampfwaffe 
WHERE contains(this.Angriff.Waffen, file.link)
SORT file.name
```