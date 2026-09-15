```dataviewjs 
const maxSpellPoints = dv.page(dv.current().Hintergrund.Klasse).Zaubereipunkte["Stufe"+dv.current().Stufe];
const currentSpellPoints = dv.current().InputData.Zaubereipunkte;
const percentValue2 =  Math.round(currentSpellPoints / (maxSpellPoints / 100));
 
 const metaBindCode = `<div style="display: flex; align-items: center; width: 100%; position: relative;"><div style="flex: 1; position: relative;"><progress id="spellpoints" max="${maxSpellPoints}" value="${currentSpellPoints}" style="width: 100%; height: 20px; --progress: rgb(57, 159, 148) !important;"></progress><span id="percentage3" style="position: absolute; left: 50%; top: 50%; transform: translate(-50%, -70%); color: white; font-weight: bold;">Zaubereipunkte</span></div><div style="width: 60px; text-align: center;">${percentValue2}%</div></div>`; 
dv.el('div', metaBindCode); 
```