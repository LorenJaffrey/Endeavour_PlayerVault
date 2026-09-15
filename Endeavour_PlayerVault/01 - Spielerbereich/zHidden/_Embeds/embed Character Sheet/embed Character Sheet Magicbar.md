```dataviewjs 
const maxGrad1 = dv.page(dv.current().Hintergrund.Klasse).Zauberplätze["Stufe"+dv.current().Stufe].Grad1;
const maxGrad2 = dv.page(dv.current().Hintergrund.Klasse).Zauberplätze["Stufe"+dv.current().Stufe].Grad2;
const maxGrad3 = dv.page(dv.current().Hintergrund.Klasse).Zauberplätze["Stufe"+dv.current().Stufe].Grad3;
const maxGrad4 = dv.page(dv.current().Hintergrund.Klasse).Zauberplätze["Stufe"+dv.current().Stufe].Grad4;
const maxGrad5 = dv.page(dv.current().Hintergrund.Klasse).Zauberplätze["Stufe"+dv.current().Stufe].Grad5;
const maxGrad6 = dv.page(dv.current().Hintergrund.Klasse).Zauberplätze["Stufe"+dv.current().Stufe].Grad6;
const maxGrad7 = dv.page(dv.current().Hintergrund.Klasse).Zauberplätze["Stufe"+dv.current().Stufe].Grad7;
const maxGrad8 = dv.page(dv.current().Hintergrund.Klasse).Zauberplätze["Stufe"+dv.current().Stufe].Grad8;
const maxGrad9 = dv.page(dv.current().Hintergrund.Klasse).Zauberplätze["Stufe"+dv.current().Stufe].Grad9;

const maxSpellSlots =  (maxGrad1*1)+(maxGrad2*4)+(maxGrad3*9)+(maxGrad4*16)+(maxGrad5*25)+(maxGrad6*36)+(maxGrad7*49)+(maxGrad8*64)+(maxGrad9*81);
 
const grad1 = dv.current().InputData.Zauberplätze.Grad_1;
const grad2 = dv.current().InputData.Zauberplätze.Grad_2;
const grad3 = dv.current().InputData.Zauberplätze.Grad_3;
const grad4 = dv.current().InputData.Zauberplätze.Grad_4;
const grad5 = dv.current().InputData.Zauberplätze.Grad_5;
const grad6 = dv.current().InputData.Zauberplätze.Grad_6;
const grad7 = dv.current().InputData.Zauberplätze.Grad_7;
const grad8 = dv.current().InputData.Zauberplätze.Grad_8;
const grad9 = dv.current().InputData.Zauberplätze.Grad_9;
 
const currentSpellSlots = (grad1*1)+(grad2*4)+(grad3*9)+(grad4*16)+(grad5*25)+(grad6*36)+(grad7*49)+(grad8*64)+(grad9*81);
const percentValue = Math.round(currentSpellSlots / (maxSpellSlots / 100));

const metaBindCode = `<div style="display: flex; align-items: center; width: 100%; position: relative;"><div style="flex: 1; position: relative;"><progress id="magic" max="${maxSpellSlots}" value="${currentSpellSlots}" style="width: 100%; height: 20px; --progress: rgb(11, 59, 163) !important;"></progress><span id="percentage2" style="position: absolute; left: 50%; top: 50%; transform: translate(-50%, -70%); color: white; font-weight: bold;">Magie</span></div><div style="width: 60px; text-align: center;">${percentValue}%</div></div>`; 
dv.el('div', metaBindCode); 
```