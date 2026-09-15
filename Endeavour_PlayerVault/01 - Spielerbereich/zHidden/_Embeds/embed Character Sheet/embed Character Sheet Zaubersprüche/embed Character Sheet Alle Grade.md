## Zaubertricks
```dataviewjs
const diceRoller = (damage) => {
  // If damage is not defined, return a placeholder
  if (!damage) return "";
  // Otherwise, format it as a dice roller command
  return `\`dice: ${damage}|none|noform\``;
};

// Function to get the appropriate damage based on the current level
const getDamageByLevel = (level, p) => {
  if (level >= 17 && p.SchadenLv17) {
    return diceRoller(p.SchadenLv17);
  } else if (level >= 11 && p.SchadenLv11) {
    return diceRoller(p.SchadenLv11);
  } else if (level >= 5 && p.SchadenLv5) {
    return diceRoller(p.SchadenLv5);
  } else {
    return diceRoller(p.Schaden);
  }
};

const magicRank = 0;

const results = dv.pages("#Zauber")
  .where(p => p.Grad == magicRank && dv.current().Zauber.some(link => link.path === p.file.path))
  .sort(p => p.file.name) // sekundäre Sortierung zuerst
  .sort(p => p.Typ); // primäre Sortierung zuletzt


if (results.length > 0) {

  dv.table(
    ["Typ", "Zauber", "Schule", "Zeitaufwand", "Schadensart", "Schaden", "Ziel", "Reichweite", "Verbal", "Geste", "Dauer", "Konzentration", "Ritual"],
    results.map(p => [
      p.Typ,
      p.file.link,
      p.Schule,
      p.Zeitaufwand,
      p.Schadensart,
      getDamageByLevel(dv.page(dv.current().Charakter).Stufe, p),  // Dynamic Schaden based on level
      p.Ziel,
      p.Reichweite,
      p.Verbal ? "X" : "",
      p.Geste ? "X" : "",
      p.Dauer,
      p.Konzentration ? "X" : "",
      p.Ritual ? "X" : ""
    ])
  );

  // Apply CSS to center headers and column content
  const table = this.container.querySelector("table");
  table.style.width = "100%";

  // Center align headers and table cells
  const headers = table.querySelectorAll("th");
  headers.forEach(header => header.style.textAlign = "center");

  const cells = table.querySelectorAll("td");
  cells.forEach(cell => cell.style.textAlign = "center");

}
```

```dataviewjs
const diceRoller = (damage) => {
  if (!damage) return "";
  return `\`dice: ${damage}|none|noform\``;
};

// Loop through magic ranks 1 to 9
for (let magicRank = 1; magicRank <= 9; magicRank++) {

  // Get all matching pages for the current magic rank
  const results = dv.pages("#Zauber")
    .where(p => p.Grad == magicRank && dv.current().Zauber.some(link => link.path === p.file.path))
    .sort(p => p.file.name) // sekundäre Sortierung zuerst
    .sort(p => p.Typ); // primäre Sortierung zuletzt

  // Only display the table if there are results for the current rank
  if (results.length > 0) {

    // Display a header for the current magic rank
    dv.header(2, `Grad ${magicRank}`);

    // Generate the table for the current magic rank
    dv.table(
      ["Typ", "Zauber", "Schule", "Zeitaufwand", "Schadensart", "Schaden", "Ziel", "Reichweite", "Verbal", "Geste", "Dauer", "Konzentration", "Ritual"],
      results.map(p => [
        p.Typ,
        p.file.link,
        p.Schule,
        p.Zeitaufwand,
        p.Schadensart,
        diceRoller(p.Schaden),   // Schaden as dice roller command
        p.Ziel,
        p.Reichweite,
        p.Verbal ? "X" : "",
        p.Geste ? "X" : "",
        p.Dauer,
        p.Konzentration ? "X" : "",
        p.Ritual ? "X" : ""
      ])
    );

    const headings = this.container.querySelectorAll('h2');
    let table = null;

    // Loop through each <h2> to find the one containing the desired span
    headings.forEach((heading) => {
      const span = heading.querySelector('span');
      if (span && span.textContent.includes(`Grad ${magicRank}`)) {
        // If the <span> contains the correct text, get the following <div> and its table
        const nextDiv = heading.nextElementSibling; // This gets the next sibling (which should be a <div>)
        if (nextDiv && nextDiv.tagName === 'DIV') {
          table = nextDiv.querySelector('table'); // Find the table inside the div

          // Apply styles to the table and its contents
          if (table) {
            // Set the table width to 100%
            table.style.width = "100%";

            // Style headers
            const headers = table.querySelectorAll("th");
            headers.forEach(header => header.style.textAlign = "center");

            // Style table cells (td)
            const cells = table.querySelectorAll("td");
            cells.forEach(cell => cell.style.textAlign = "center");
          }
        }
      }
    });

  }
}
```