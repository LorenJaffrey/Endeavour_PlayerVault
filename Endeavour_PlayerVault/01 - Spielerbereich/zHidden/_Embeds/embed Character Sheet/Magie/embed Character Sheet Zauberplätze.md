```dataviewjs
const klasse = dv.current().Hintergrund.Klasse;
const stufe = dv.current().Stufe;
const klasseSeite = dv.page(klasse);
const zauberplaetze = klasseSeite.Zauberplätze["Stufe" + stufe];

let output = "| Grad | [[Zauberplätze]] Maximal | [[Zauberplätze]] Aktuell |\n";
output += "|:----:|:--------:|:--------:|\n";

for (let grad = 1; grad <= 9; grad++) {
  const max = zauberplaetze["Grad" + grad];
  if (max > 0) {
    output += `| ${grad} | ${max} | \`INPUT[number():InputData.Zauberplätze.Grad_${grad}]\` |\n`;
  }
}

dv.paragraph(output);
```