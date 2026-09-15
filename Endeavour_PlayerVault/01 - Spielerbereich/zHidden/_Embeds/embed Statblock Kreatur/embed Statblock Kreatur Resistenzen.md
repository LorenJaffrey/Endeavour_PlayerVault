``` dataviewjs
var schadensresistenzen = dv.current().Verteidigung.Resistenzen.Schadensresistenz;
var schadensimmunitäten = dv.current().Verteidigung.Resistenzen.Schadensimmunität;
var schadensanfälligkeiten = dv.current().Verteidigung.Resistenzen.Schadensanfälligkeit;
var zustandsimmunitäten = dv.current().Verteidigung.Resistenzen.Zustandsimmunität;


var schadensresistenzenString = "";
var schadensimmunitätenString = "";
var schadensanfälligkeitenString = "";
var zustandsimmunitätenString = "";
var resistenzenString = "";

if (schadensresistenzen) {
	schadensresistenzenString += "#### Schadensresistenzen";
	for (var i = 0, j = schadensresistenzen.length; i<j; i++) {
		schadensresistenzenString += "\n - " + schadensresistenzen[i];
	}
}

if (schadensimmunitäten) {
	schadensimmunitätenString += "#### Schadensimmunitäten";
	for (var i = 0, j = schadensimmunitäten.length; i<j; i++) {
		schadensimmunitätenString +=  "\n - " + schadensimmunitäten[i];
	}
}

if (schadensanfälligkeiten) {
	schadensanfälligkeitenString += "#### Schadensanfälligkeiten";
	for (var i = 0, j = schadensanfälligkeiten.length; i<j; i++) {
		schadensanfälligkeitenString +=  "\n - " + schadensanfälligkeiten[i];
	}
}

if (zustandsimmunitäten) {
	zustandsimmunitätenString += "#### Zustandsimmunitäten";
	for (var i = 0, j = zustandsimmunitäten.length; i<j; i++) {
		zustandsimmunitätenString +=  "\n - " + zustandsimmunitäten[i];
	}
}

if (schadensresistenzenString) {
	resistenzenString += schadensresistenzenString;
}
if (schadensimmunitätenString) {
	if (resistenzenString) {
		resistenzenString += "\n"
	}
	resistenzenString += schadensimmunitätenString;
}
if (schadensanfälligkeitenString) {
	if (resistenzenString) {
		resistenzenString += "\n"
	}
	resistenzenString += schadensanfälligkeitenString;
}
if (zustandsimmunitätenString) {
	if (resistenzenString) {
		resistenzenString += "\n"
	}
	resistenzenString += zustandsimmunitätenString;
}
if (resistenzenString) {
	resistenzenString = "### Resistenzen\n" + resistenzenString;
	dv.span(resistenzenString);
}
```