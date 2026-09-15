```dataviewjs
const skills = dv.current().Fertigkeiten;
var string = ""; 
for (var key in skills) {
	if(skills[key] > 0) {
		if (string.length > 0) {
			string += "\n";
		}
		string += "- [[" + key.replaceAll("_"," ") + "]]: +" + (skills[key]*(Math.ceil(dv.current().Herausforderungsgrad/4)+1) + Math.floor((dv.current().Attribute[dv.page(dv.page(key.replaceAll("_"," ")).Attribut).file.name]-10)/2));
	}
}
dv.paragraph(string);
```

[[Wahrnehmung#Passive Wahrnehmung]]: `=10+floor(((this.Attribute.Weisheit)-10)/2)+(this.Fertigkeiten.Wahrnehmung*(ceil(this.Herausforderungsgrad/4)+1))`