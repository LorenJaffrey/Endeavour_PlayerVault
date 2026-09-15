# `=this.file.name`

``` dataview
TABLE Ordnung, Moral
FROM #Charakter/GORN 
SORT file.name
```

---

| Charakter | Ordnung | Moral | Ordnung | Moral |
| --------- |:-------:|:-----:|:-------:|:-----:|
| Aranon    |    3    |   3   |   0.8   |  0.8  |
| Drogan    |    2    |   4   |   0.7   |  0.9  |
| Lucian    |   -3    |  -1   |   0.2   |  0.4  |
| Niptac    |   -2    |   1   |   0.3   |  0.6  |
| [[Ar'go]] |    1    |   2   |   0.6   |  0.7  |
<!-- TBLFM: $4=(($-2+5)/10) -->
<!-- TBLFM: $5=(($-2+5)/10) -->

---

|            | -4 Chaotisch | -3 Chaotisch | -2 Chaotisch | -1 Neutral | 0 Neutral | 1 Neutral | 2 Rechtschaffen | 3 Rechtschaffen | 4 Rechtschaffen |
|:----------:|:------------:|:------------:|:------------:|:----------:|:---------:|:---------:|:---------------:|:---------------:|:---------------:|
|   4 Gut    |              |              |              |            |           |           |     Drogan      |                 |                 |
|   3 Gut    |              |              |              |            |           |           |                 |     Aranon      |                 |
|   2 Gut    |              |              |              |            |           |   Argo    |                 |                 |                 |
| 1 Neutral  |              |              |    Niptac    |            |           |           |                 |                 |              |
| 0 Neutral  |              |              |              |            |           |           |                 |                 |                 |
| -1 Neutral |              |    Lucian    |              |            |           |           |                 |                 |                 |
|  -2 Böse   |              |              |              |            |           |           |                 |                 |                 |
|  -3 Böse   |              |              |              |            |           |           |                 |                 |                 |
|  -4 Böse   |              |              |              |            |           |           |                 |                 |                 |

---

``` mermaid
%%{init: {"quadrantChart": {"chartWidth": 400, "chartHeight": 400}, "themeVariables": {"quadrant1Fill": "#000000", "quadrant2Fill": "#000000", "quadrant3Fill": "#000000", "quadrant4Fill": "#000000"} }}%%
quadrantChart
    title Gesinnung PFT
    x-axis Chaotisch --> Rechtschaffen
    y-axis Boese --> Gut
    quadrant-1 Rechtschaffen Gut
    quadrant-2 Chaotisch Gut
    quadrant-3 Chaotisch Boese
    quadrant-4 Rechtschaffen Boese
    Aranon: [0.8, 0.8]
    Drogan: [0.7, 1]
    Argo: [0.6, 0.7]
    Lucian: [0.2, 0.4]
    Niptac: [0.3, 0.6]
```