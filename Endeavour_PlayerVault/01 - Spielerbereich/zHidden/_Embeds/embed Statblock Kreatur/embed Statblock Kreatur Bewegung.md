```dataviewjs
const movement = dv.current().Bewegung;
var string = "<table><thead><tr><th></th><th></th></tr></thead><tbody>";
for (var key in movement) {
	if (movement[key] > 0) {
		string += "<tr><td><a href='[[ " + key + " ]]'>" + key + "</a></td><td>" + movement[key] + "m (" + (movement[key] / 1.5) + " Kästchen)</td></tr>";
	}
}
string += "</tbody></table>";
dv.paragraph(string);

```