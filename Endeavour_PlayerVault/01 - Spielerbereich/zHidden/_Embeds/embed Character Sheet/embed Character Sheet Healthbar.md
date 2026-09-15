```dataviewjs 
const Gesundheit = dv.current().Gesundheit; 
const percentage = Math.round((Gesundheit.TP / Gesundheit.MaxTP) * 100);
const metaBindCode = `<div style="display: flex; align-items: center; width: 100%; position: relative;"><div style="flex: 1; position: relative;"><progress id="health" max="${Gesundheit.MaxTP}" value="${Gesundheit.TP}" style="width: 100%; height: 20px;"></progress><span id="percentage" style="position: absolute; left: 50%; top: 50%; transform: translate(-50%, -70%); color: white; font-weight: bold;">Gesundheit</span></div><div style="width: 60px; text-align: center;">${percentage}%</div></div>`; 
dv.el('div', metaBindCode); 
```