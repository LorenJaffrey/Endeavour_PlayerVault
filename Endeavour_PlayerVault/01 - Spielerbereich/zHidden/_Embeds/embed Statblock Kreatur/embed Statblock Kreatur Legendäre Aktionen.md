``` dataviewjs
var legendäreAktionen = dv.current().Legendäre_Aktionen;
var anzahlLegendäreAktionen = dv.current().Anzahl_Legendäre_Aktionen;
var legendäreAktionenString = "";

if (legendäreAktionen) {
	for (var i = 0, j = legendäreAktionen.length; i<j; i++) {
		legendäreAktionenString += "\n- "
		legendäreAktionenString += legendäreAktionen[i];
	}
	legendäreAktionenString = "### Legendäre Aktionen\n" + "Anzahl: " + anzahlLegendäreAktionen + "\n" + legendäreAktionenString;
	dv.span(legendäreAktionenString);
}
```