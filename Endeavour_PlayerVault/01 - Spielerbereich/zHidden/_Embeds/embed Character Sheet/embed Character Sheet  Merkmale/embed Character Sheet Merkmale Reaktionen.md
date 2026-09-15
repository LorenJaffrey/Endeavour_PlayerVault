``` dataviewjs
let merkmale = dv.current().Merkmale;
let reaktionen = [];
let reaktionenString = '';
let aktuellesMerkmal;

dv.span('#### Reaktionen');

if (merkmale) {
	for (let aktuellesMerkmal of merkmale) {
		if (typeof(dv.page(aktuellesMerkmal).Einsatz) == 'object') {
			if (dv.page(dv.page(aktuellesMerkmal).Einsatz).file.name == 'Reaktion')  {
				reaktionen.push(aktuellesMerkmal);
			}
		}
	}

	if (reaktionen.length > 0) {
		for (var i = 0, j = reaktionen.length; i<j; i++) {
			reaktionenString +=  "\n - " + reaktionen[i];
		}
		reaktionenString += '\n'
		dv.span(reaktionenString);
	}
}	
let standardReaktionen = dv.pages('#Zug/Reaktion').sort(page => page.file.name);
let standardReaktionenString = '';
for (let reaktion of standardReaktionen) {
	standardReaktionenString += '\n - [[' + reaktion.file.name + ']]';
}

dv.span(standardReaktionenString);
```