```dataviewjs
const title = dv.current().Hintergrund.Name;

dv.paragraph(`
  <h1 style="
    text-shadow: 
      0 0 10px rgba(155, 65, 65, 0.8),
      0 0 20px rgba(139, 0, 0, 0.6),
      0 0 30px rgba(110, 0, 0, 0.4);
    padding: 20px;
    border-radius: 10px;
    text-align: center;
    animation: blitzAnimation 2s infinite;
    --font-weight: var(--h1-weight);
    font-variant: var(--h1-variant);
    letter-spacing: -0.015em;
    line-height: var(--h1-line-height);
    font-size: 4em;
    color: var(--h1-color);
    font-weight: var(--font-weight);
    font-style: var(--h1-style);
    font-family: var(--h1-font);
  "> ${title} </h1>
`);
```