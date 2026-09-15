``` dataviewjs
var merkmale = dv.current().Merkmale;
var aktionen = [];
var bonusaktionen = [];
var reaktionen = [];
var passiv = [];

var merkmaleString = "";
var aktionenString = "";
var bonusaktionenString = "";
var reaktionenString = "";
var passivString = "";

var aktuellesMerkmal;

if (merkmale) {
	for (var i = 0, j = merkmale.length; i<j; i++) {
		aktuellesMerkmal = dv.page(merkmale[i]);
		if (typeof(aktuellesMerkmal.Einsatz) == "object") {
			if (dv.page(aktuellesMerkmal.Einsatz).file.name == dv.parse("[[Aktion]]").path)  {
				aktionen.push(merkmale[i]);
			}
			if (dv.page(aktuellesMerkmal.Einsatz).file.name == dv.parse("[[Bonusaktion]]").path)  {
				bonusaktionen.push(merkmale[i]);
			}
			if (dv.page(aktuellesMerkmal.Einsatz).file.name == dv.parse("[[Reaktion]]").path)  {
				reaktionen.push(merkmale[i]);
			}
		}
		else {
			passiv.push(merkmale[i]);
		}
	}
	
	if (aktionen.length > 0) {
		aktionenString += "#### Aktionen";
		for (var i = 0, j = aktionen.length; i<j; i++) {
			aktionenString += "\n - " + aktionen[i];
		}
	}
	
	if (bonusaktionen.length > 0) {
		bonusaktionenString += "#### Bonusaktionen";
		for (var i = 0, j = bonusaktionen.length; i<j; i++) {
			bonusaktionenString +=  "\n - " + bonusaktionen[i];
		}
	}
	
	if (reaktionen.length > 0) {
		reaktionenString += "#### Reaktionen";
		for (var i = 0, j = reaktionen.length; i<j; i++) {
			reaktionenString +=  "\n - " + reaktionen[i];
		}
	}
	
	if (passiv.length > 0) {
		passivString += "#### Passive Merkmale";
		for (var i = 0, j = passiv.length; i<j; i++) {
			passivString +=  "\n - " + passiv[i];
		}
	}
	
	if (aktionenString) {
		merkmaleString += aktionenString;
	}
	if (bonusaktionenString) {
		if (merkmaleString) {
			merkmaleString += "\n"
		}
		merkmaleString += bonusaktionenString;
	}
	if (reaktionenString) {
		if (merkmaleString) {
			merkmaleString += "\n"
		}
		merkmaleString += reaktionenString;
	}
	if (passivString) {
		if (merkmaleString) {
			merkmaleString += "\n"
		}
		merkmaleString += passivString;
	}
	if (merkmaleString) {
		merkmaleString = "### Merkmale\n" + merkmaleString;
		dv.span(merkmaleString);
	}
}
```