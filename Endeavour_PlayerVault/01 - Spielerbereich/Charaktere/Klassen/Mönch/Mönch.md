---
tags:
  - Regeln/Endeavour/Charakter/Klasse/WIP
BasisTP: 2
BasisRP: 1
Kernattribute:
  - "[[Beweglichkeit]]"
  - "[[Entschlossenheit]]"
Übung:
  Waffen:
    - "[[Einfache Waffen]]"
  Rüstungen:
    - keine
Rettungswürfe:
  Vorteil:
    - "[[Beweglichkeitsrettungswürfe|BW-Rettungswürfe]]"
    - "[[Entschlossenheitsrettungswürfe|EN-Rettungswürfe]]"
  Nachteil:
    - "[[Konstitutionsrettungswürfe|KO-Rettungswürfe]]"
    - "[[Präsenzrettungswürfe|PR-Rettungswürfe]]"
Beschreibung: Ein disziplinierter Kampfkünstler mit schnellen Händen und schnellen Füßen.
Mönchswürfel:
  1: 1W6
  6: 1W8
  10: 1W10
  14: 1W12
  18: 2W6
---
# `=this.file.name`
Ein [[Mönch]] widmet sein Leben dem unermüdlichen Streben nach kinetischer Perfektion. 
Sie stählen ihre Körper, bis sie zu einem verschwommenen Abbild reiner Bewegung werden. 
Sie trainieren von frühester Kindheit an in abgelegener Wildnis oder Bergklöstern und nutzen ihre Schnelligkeit, um Schläge zu entfesseln, die in ihren Feinden nachhallen und wie ein flüsternder Wind an Angriffen vorbeigleiten. Geschwindigkeit ist sowohl ihre Waffe als auch ihr Schild.
Durch rastloses Training bündeln sie ihren inneren Schwung, um Taten übernatürlicher Beweglichkeit zu vollbringen und jede Bewegung mit fließender Präzision auszuführen. 

Der [[Mönch]] ist:
- **Unbewaffnet und gefährlich.** Unbewaffnet und ohne Rüstung bist du eine unaufhaltsame Macht auf dem Schlachtfeld. 
  Stecke Schläge ein und lande verheerende Treffer, die deine Feinde in Staunen über deine Zähigkeit und Geschwindigkeit versetzen.    
- **Ein anmutiger Kämpfer.** Bewege dich mit beispielloser Schnelligkeit und Entschlossenheit und hänge Freunde wie Feinde ab. 
  Ergreife die Initiative und schlage blitzschnell zu, um sicherzustellen, dass du immer an vorderster Front kämpfst. 
  Deine Reflexe erlauben es dir, präzise zu kontern und gegnerische Schläge in Gelegenheiten für vernichtende Gegenangriffe zu verwandeln.

---

```dynamic-embed
[[embed Klasse]]
```

---

## Startausrüstung

---

## Klassentabelle

```dataviewjs
const klasse = dv.current();
const gehoertZurKlasse = (p) => {
  if (!p.Klasse) return false;
  return dv.array(p.Klasse).values.some(x => x === "Alle" || (x && x.path === klasse.file.path));
};
const istCharaktermerkmal = (p) => p.file.tags.some(t => t === "#Regeln/Endeavour/Merkmal/Klasse" || t.startsWith("#Regeln/Endeavour/Merkmal/Klasse/"));
const merkmale = dv.pages().where(p => p.Stufe !== undefined && istCharaktermerkmal(p) && gehoertZurKlasse(p)).values;
const wuerfel = klasse["Mönchswürfel"] ?? {};
const wuerfelStufen = Object.keys(wuerfel).map(Number).sort((a, b) => a - b);
const subklassen = dv.page("Subklassen " + klasse.file.name);
const reihen = [];
for (let stufe = 1; stufe <= 20; stufe++) {
  const hier = merkmale.filter(p => dv.array(p.Stufe).values.includes(stufe));
  const basis = hier.filter(p => !p.Subklasse).sort((a, b) =>
    (a.Klasse === "Alle" ? 0 : 1) - (b.Klasse === "Alle" ? 0 : 1) ||
    a.file.name.localeCompare(b.file.name, "de"));
  const links = basis.map(p => `[[${p.file.path}|${p.file.name}]]`);
  if (subklassen && (stufe === 3 || hier.some(p => p.Subklasse))) {
    links.push(`[[${subklassen.file.path}|${stufe === 3 ? "Mönch Subklasse" : "Subklassen Merkmal"}]]`);
  }
  const w = [...wuerfelStufen].reverse().find(s => s <= stufe);
  reihen.push([stufe, wuerfel[w], links.join(", ")]);
}
dv.table(["Stufe", "Mönchswürfel", "Merkmale"], reihen);
```
