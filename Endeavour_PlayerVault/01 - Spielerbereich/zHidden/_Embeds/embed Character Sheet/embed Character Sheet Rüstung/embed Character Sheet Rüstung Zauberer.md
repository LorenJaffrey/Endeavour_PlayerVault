```dataviewjs
const page = dv.current();

const input = page.InputData ?? {};
const attr = page.Attribute ?? {};
const def = page.Verteidigung ?? {};

const geschick = attr.Geschicklichkeit ?? 10;
const geschickMod = Math.floor((geschick - 10) / 2);
const zusatzRüstung = def.Zusätzliche_Rüstung ?? 0;

let rüstungsklasse = 0;
let rkTooltip = "";
if (input.MagierRüstung === true) {
    const schild = def.Schild?.RP ?? def.Schild ?? 0;
    rüstungsklasse = 13 + geschickMod + schild + zusatzRüstung;
    rkTooltip = `13 (Magier-Rüstung) + ${geschickMod} (Geschick aus ${geschick}) + ${schild} (Schild) + ${zusatzRüstung} (Zusatz)`;
} else {
    const natRüstung = def.Natürliche_Rüstung ?? 0;
    const rüstungRP = def.Rüstung?.RP ?? def.Rüstung ?? 0;
    rüstungsklasse = natRüstung + geschickMod + rüstungRP + zusatzRüstung;
    rkTooltip = `${natRüstung} (Natürliche Rüstung) + ${geschickMod} (Geschick aus ${geschick}) + ${rüstungRP} (Rüstung) + ${zusatzRüstung} (Zusatz)`;
}

const rüstungSR = def.Rüstung?.SR ?? 0;
const schildSR = def.Schild?.SR ?? 0;
const schadensreduktion = rüstungSR + schildSR;
const srTooltip = `${rüstungSR} (Rüstung SR) + ${schildSR} (Schild SR)`;

// Tooltip-Icons
const infoIcon = (tooltip) => `<span title="${tooltip}" style="cursor: help;">🔎</span>`;

// Markdown-Tabelle mit HTML-Tooltips bei den Zahlen
let table = `| [[Rüstungsklasse]] | [[Schadensreduktion]] |\n`;
table += `| :--------------------: | :------------------------: |\n`;
table += `| ${rüstungsklasse} ${infoIcon(rkTooltip)} | ${schadensreduktion} ${infoIcon(srTooltip)} |\n`;

dv.paragraph(table);

```

|    Beschreibung     |           Bonus (bereits eingerechnet)           |
|:-------------------:|:------------------------------------------------:|
| Zusätzliche Rüstung | `INPUT[number:Verteidigung.Zusätzliche_Rüstung]` |
