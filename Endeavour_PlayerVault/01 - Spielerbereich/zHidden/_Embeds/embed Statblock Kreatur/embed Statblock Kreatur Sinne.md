``` dataviewjs
var sinne = dv.current().Sinne;
var sinneString = "";

if (sinne) {
	sinneString += "## Sinne";
	for (var i = 0, j = sinne.length; i<j; i++) {
		sinneString +=   "\n - " + sinne[i];
	}
	dv.span(sinneString);
}
```