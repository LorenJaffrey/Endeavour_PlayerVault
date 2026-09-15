``` dataviewjs
let merkmale = dv.current().Merkmale;
let bonusaktionen = [];
let bonusaktionenString = '';
let aktuellesMerkmal;

dv.span('#### Bonusaktionen');

if (merkmale) {
	for (let aktuellesMerkmal of merkmale) {
		if (typeof(dv.page(aktuellesMerkmal).Einsatz) == 'object') {
			if (dv.page(dv.page(aktuellesMerkmal).Einsatz).file.name == 'Bonusaktion')  {
				bonusaktionen.push(aktuellesMerkmal);
			}
		}
	}

	if (bonusaktionen.length > 0) {
		for (var i = 0, j = bonusaktionen.length; i<j; i++) {
			bonusaktionenString += '\n - ' + bonusaktionen[i];
		}
		bonusaktionenString += '\n'
		dv.span(bonusaktionenString);
	}
}

let standardBonusaktionen = dv.pages('#Zug/Bonusaktion').sort(page => page.file.name);
let standardBonusaktionenString = '';
for (let bonusaktion of standardBonusaktionen) {
	standardBonusaktionenString += '\n - [[' + bonusaktion.file.name + ']]';
}

dv.span(standardBonusaktionenString);
```