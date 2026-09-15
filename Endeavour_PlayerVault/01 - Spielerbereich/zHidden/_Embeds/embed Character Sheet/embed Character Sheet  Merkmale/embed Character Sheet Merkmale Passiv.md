``` dataviewjs
var merkmale = dv.current().Merkmale;
var passiv = [];
var passivString = "#### Passive Merkmale";
var aktuellesMerkmal;

if (merkmale) {
	for (var i = 0, j = merkmale.length; i<j; i++) {
		aktuellesMerkmal = dv.page(merkmale[i]);
		if (typeof(aktuellesMerkmal.Einsatz) !== "object") {
			passiv.push(merkmale[i]);
		}
	}
	
	if (passiv.length > 0) {
		for (var i = 0, j = passiv.length; i<j; i++) {
			passivString +=  "\n - " + passiv[i];
		}
	}
	dv.span(passivString);
}
```