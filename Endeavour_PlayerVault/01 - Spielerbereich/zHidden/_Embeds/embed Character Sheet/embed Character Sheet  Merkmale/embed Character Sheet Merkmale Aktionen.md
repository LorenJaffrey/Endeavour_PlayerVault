``` dataviewjs
let merkmale = dv.current().Merkmale;
let aktionen = [];
let aktionenString = '';
let aktuellesMerkmal;

dv.span('#### Aktionen');

if (merkmale) {
	for (let aktuellesMerkmal of merkmale) {
		if (typeof(dv.page(aktuellesMerkmal).Einsatz) == 'object') {
			if (dv.page(dv.page(aktuellesMerkmal).Einsatz).file.name == 'Aktion')  {
				aktionen.push(aktuellesMerkmal);
			}
		}
	}
	
	if (aktionen.length > 0) {
		for (var i = 0, j = aktionen.length; i<j; i++) {
			aktionenString += '\n - ' + aktionen[i];
		}
		aktionenString += '\n'
		dv.span(aktionenString);
	}
}

let standardAktionen = dv.pages('#Zug/Aktion').sort(page => page.file.name);
let standardAktionenString = '';
for (let aktion of standardAktionen) {
	standardAktionenString += '\n - [[' + aktion.file.name + ']]';
}

dv.span(standardAktionenString);
```