> [!infobox|left]
> <canvas id="radarChart" width="288" height="288" style="border: none;"></canvas>
> 
> ```dataviewjs 
> dv.el('h2', `<h2>Stärke</h2>`); 
> ```
> ```dynamic-embed
> [[embed Character Sheet Attribute Stärke]]
> ```
>
> ```dataviewjs 
> dv.el('h2', `<h2>Geschicklichkeit</h2>`); 
> ```
> ```dynamic-embed
> [[embed Character Sheet Attribute Geschicklichkeit]]
> ```
>
> ```dataviewjs 
> dv.el('h2', `<h2>Konstitution</h2>`); 
> ```
> ```dynamic-embed
> [[embed Character Sheet Attribute Konstitution]]
> ```
>
> ```dataviewjs 
> dv.el('h2', `<h2>Intelligenz</h2>`); 
> ```
> ```dynamic-embed
> [[embed Character Sheet Attribute Intelligenz]]
> ```
>
> ```dataviewjs 
> dv.el('h2', `<h2>Weisheit</h2>`); 
> ```
> ```dynamic-embed
> [[embed Character Sheet Attribute Weisheit]]
> ```
>
> ```dataviewjs 
> dv.el('h2', `<h2>Charisma</h2>`); 
> ```
> ```dynamic-embed
> [[embed Character Sheet Attribute Charisma]]
> ```
>

```js-engine

//Anfang - Radardiagramm

function initializeRadarChart() {
    const canvas = document.getElementById('radarChart');
    if (!canvas) {
        // Retry after a short delay if the canvas is not yet in the DOM
        setTimeout(initializeRadarChart, 100);
        return;
    }

    const ctx = canvas.getContext('2d');
    const staerke = context.metadata.frontmatter.Attribute.Stärke;
	const geschicklichkeit = context.metadata.frontmatter.Attribute.Geschicklichkeit;
	const konstitution = context.metadata.frontmatter.Attribute.Konstitution;
	const intelligenz = context.metadata.frontmatter.Attribute.Intelligenz;
	const weisheit = context.metadata.frontmatter.Attribute.Weisheit;
	const charisma = context.metadata.frontmatter.Attribute.Charisma;

    // Werte für die Charaktere
    const data = {
        labels: ['STA', 'GES', 'KON', 'INT', 'WEI', 'CHA'],
        //values: [10, 13, 16, 12, 10, 18],
        values: [staerke, geschicklichkeit, konstitution, intelligenz, weisheit, charisma],
        maxValue: 20
    };

    // Zentrum und Radius des Radardiagramms (angepasst für 288px)
    const centerX = canvas.width / 2;
    const centerY = canvas.height / 2;
    const radius = 110; // Anpassen des Radius für die neue Größe

    // Anzahl der Eigenschaften
    const numAttributes = data.labels.length;

    // Zeichne das Radar mit Kreisen und Linien
    function drawRadar() {
        ctx.strokeStyle = '#999';
        ctx.lineWidth = 1;
        // Kreise zeichnen (Skalenringe)
        for (let i = 1; i <= 5; i++) {
            const currentRadius = (radius / 5) * i;
            ctx.beginPath();
            ctx.arc(centerX, centerY, currentRadius, 0, Math.PI * 2);
            ctx.stroke();
        }

        // Achsen zeichnen
        for (let i = 0; i < numAttributes; i++) {
            const angle = (Math.PI * 2 / numAttributes) * i;
            const x = centerX + Math.cos(angle) * radius;
            const y = centerY + Math.sin(angle) * radius;
            ctx.beginPath();
            ctx.moveTo(centerX, centerY);
            ctx.lineTo(x, y);
            ctx.stroke();

            // Fettgedruckte Beschriftung der Achsen
            ctx.fillStyle = '#ffffff';
            ctx.font = 'bold 12px Arial'; // Schriftgröße anpassen
            const labelX = centerX + Math.cos(angle) * (radius + 15); // Etwas näher an den Rand
            const labelY = centerY + Math.sin(angle) * (radius + 15);
            ctx.fillText(data.labels[i], labelX - 10, labelY + 5);
        }
    }

    // Zeichne die Datenlinie und schattiere den inneren Bereich
    function drawDataLine() {
        ctx.clearRect(0, 0, canvas.width, canvas.height); // Canvas löschen
        drawRadar(); // Das Radar erneut zeichnen

        // Schattierter Bereich
        ctx.fillStyle = 'rgba(0, 123, 255, 0.2)';
        ctx.beginPath();
        for (let i = 0; i < numAttributes; i++) {
            const value = data.values[i];
            const ratio = value / data.maxValue;
            const angle = (Math.PI * 2 / numAttributes) * i;
            const x = centerX + Math.cos(angle) * radius * ratio;
            const y = centerY + Math.sin(angle) * radius * ratio;

            if (i === 0) {
                ctx.moveTo(x, y);
            } else {
                ctx.lineTo(x, y);
            }
        }
        ctx.closePath();
        ctx.fill(); // Schattierung füllen

        // Linien zeichnen
        ctx.strokeStyle = '#007bff';
        ctx.lineWidth = 2;
        ctx.beginPath();
        for (let i = 0; i < numAttributes; i++) {
            const value = data.values[i];
            const ratio = value / data.maxValue;
            const angle = (Math.PI * 2 / numAttributes) * i;
            const x = centerX + Math.cos(angle) * radius * ratio;
            const y = centerY + Math.sin(angle) * radius * ratio;

            if (i === 0) {
                ctx.moveTo(x, y);
            } else {
                ctx.lineTo(x, y);
            }
        }
        ctx.closePath();
        ctx.stroke();

        // Punkte auf den Datenlinien zeichnen
        ctx.fillStyle = '#007bff';
        for (let i = 0; i < numAttributes; i++) {
            const value = data.values[i];
            const ratio = value / data.maxValue;
            const angle = (Math.PI * 2 / numAttributes) * i;
            const x = centerX + Math.cos(angle) * radius * ratio;
            const y = centerY + Math.sin(angle) * radius * ratio;
            ctx.beginPath();
            ctx.arc(x, y, 4, 0, Math.PI * 2);
            ctx.fill();
        }
    }

    // Radar zeichnen und Datenlinie anzeigen
    drawRadar();
    drawDataLine();
}

// Run the function
initializeRadarChart();

//Ende - Radardiagramm
```