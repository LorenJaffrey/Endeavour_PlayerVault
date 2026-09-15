```dataviewjs
const page = dv.current();
const klasse = page.Hintergrund?.Klasse;
const zauberAttrPage = dv.page(klasse)?.Zauberattribut;
const zauberAttrName = dv.page(zauberAttrPage)?.file.name ?? "Unbekannt";
const attrWert = page.Attribute?.[zauberAttrName] ?? 10;
const stufe = page.Stufe ?? 1;
const intuitive = page.InputData?.IntuitiveZaubereiAktiv === true;

const profBonus = Math.ceil(stufe / 4) + 1;
const attrMod = Math.floor((attrWert - 10) / 2);
const angriffBonus = profBonus + attrMod;
const bonus = profBonus + attrMod + (intuitive ? 1 : 0);
const sg = 8 + bonus;

const tooltipAngriff = `${profBonus} (Übung) + ${attrMod} (${zauberAttrName} ${attrWert}) = ${angriffBonus}`;
const tooltipSG = `8 + ${profBonus} (Übung) + ${attrMod} (${zauberAttrName} ${attrWert})${intuitive ? " + 1 (Intuitive Zauberei)" : ""}`;

// Funktion zum Ersetzen bestimmter Textmarker im gesamten HTML
function replaceTooltipMarker(marker, tooltipText) {
    const walker = document.createTreeWalker(document.body, NodeFilter.SHOW_TEXT, null, false);
    let node;

    while ((node = walker.nextNode())) {
        const idx = node.nodeValue.indexOf(marker);
        if (idx !== -1) {
            const before = node.nodeValue.slice(0, idx);
            const after = node.nodeValue.slice(idx + marker.length);
            const beforeNode = document.createTextNode(before);
            const afterNode = document.createTextNode(after);
            const span = document.createElement("span");
            span.innerText = "🔎";
            span.title = tooltipText;
            span.style.cursor = "help";

            const parent = node.parentNode;
            parent.replaceChild(afterNode, node);
            parent.insertBefore(span, afterNode);
            parent.insertBefore(beforeNode, span);
        }
    }
}

// Jetzt die Platzhalter ersetzen
replaceTooltipMarker("tooltipZauberangriff", tooltipAngriff);
replaceTooltipMarker("tooltipZauberrettungswurf", tooltipSG);

```

| [[Zauberattribut]]                                          |                                                                       Zauberangriffsbonus `$=dv.current().InputData.IntuitiveZaubereiAktiv===true?"(VORTEIL!)":""`                                                                      |                                                                       [[Zauberrettungswurf-Schwierigkeitsgrad\|Zauberrettungswurf-SG]]                                                                       |
| :-----------------------------------------------------------: |:---------------------------------------------------------------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| `$=dv.page(dv.current().Hintergrund.Klasse).Zauberattribut` |`$="```dice:1d20+" + (Math.ceil((dv.current().Stufe/4)+1)+Math.floor(((dv.current().Attribute[dv.page(dv.page(dv.current().Hintergrund.Klasse).Zauberattribut).file.name])-10)/2)) + "\|none\|noform\```"` `$=dv.current().InputData.IntuitiveZaubereiAktiv===true?(" & ```dice:1d20+" + (Math.ceil((dv.current().Stufe/4)+1)+Math.floor(((dv.current().Attribute[dv.page(dv.page(dv.current().Hintergrund.Klasse).Zauberattribut).file.name])-10)/2)) + "\|none\|noform\```"):""` tooltipZauberangriff | `$=8+Math.ceil((dv.current().Stufe/4)+1)+Math.floor(((dv.current().Attribute[dv.page(dv.page(dv.current().Hintergrund.Klasse).Zauberattribut).file.name])-10)/2)+(dv.current().InputData.IntuitiveZaubereiAktiv===true?1:0)` tooltipZauberrettungswurf |