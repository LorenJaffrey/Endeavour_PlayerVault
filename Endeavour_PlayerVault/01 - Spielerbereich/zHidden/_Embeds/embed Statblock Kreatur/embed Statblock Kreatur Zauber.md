``` dataviewjs
var zauber = dv.current().Zauberwirken ? dv.current().Zauberwirken.Zauber : null;
var zauberString = "#### Zauber";
var aktuellerZauber;

if (zauber && zauber.length > 0) {
	for (var i = 0, j = zauber.length; i<j; i++) {
		zauberString +=  "\n - " + zauber[i];
	}
	dv.span(zauberString);
}
```