---
tags:
  - Regeln/Nimble
aliases:
  - Würfelklasse
---
# `=this.file.name`
Die [[Würfelklassen|Würfelklasse]] eines Wurfs entspricht dem Maximum des möglichen Ergebnisses (z.B. hat sowohl 1W4 als auch 2W2 die Würfelklasse 4, weil beide maximal 4 erzielen können). 
Sie dient als gemeinsamer Vergleichsmaßstab um Schadenswürfe unterschiedlicher Würfelanzahl und -größe einzuordnen und gezielt eine Stufe höher oder niedriger zu greifen, etwa bei der Waffeneigenschaft [[Vielseitig]].

Ungewöhnliche Würfel wie 1W3 oder 1W5 existieren nicht als physische Würfel und werden durch einen größeren, durch zwei geteilten und aufgerundeten Standardwürfel ersetzt (z.B. 1W3 = 1W6 halbiert, aufgerundet). 
Bei mehreren Würfeln (z.B. 2W3) wird jeder Würfel einzeln ersetzt und aufgerundet, nicht die Summe aller Würfel.

Die Spalte "Durchschnitt mit Vorteil" gibt den Erwartungswert an, wenn der gesamte Wurf mit [[Vorteil und Nachteil|Vorteil]] ausgeführt wird (der Wurf wird zweimal ausgeführt, das höhere Ergebnis zählt). 
Das ist relevant für Effekte die Vorteil auf Schadenswürfe gewähren, etwa besondere Waffenqualität.

Zwei Würfelkombinationen derselben Klasse haben nicht zwangsläufig denselben Durchschnitt (1W4 hat Ø2.5, 2W2 hat Ø3.0, trotz gleicher Klasse 4). 
Die Klasse ist ein Einstufungswerkzeug, keine Garantie für identische statistische Ergebnisse.

| Wurf | Klasse | Würfel                       | Durchschnitt | Durchschnitt mit Vorteil | Differenz |
| ---- | ------ | ---------------------------- | ------------ | ------------------------ | --------- |
| 1W2  | 2      | 1W4 (halbiert, aufgerundet)  | 1.50         | 1.75                     | 0.25      |
|      |        |                              |              |                          |           |
| 1W3  | 3      | 1W6 (halbiert, aufgerundet)  | 2.00         | 2.444444                 | 0.444444  |
|      |        |                              |              |                          |           |
| 1W4  | 4      | 1W4                          | 2.50         | 3.125                    | 0.625     |
| 2W2  | 4      | 2W4 (halbiert, aufgerundet)  | 3.00         | 3.375                    | 0.375     |
|      |        |                              |              |                          |           |
| 1W5  | 5      | 1W10 (halbiert, aufgerundet) | 3.00         | 3.8                      | 0.8       |
|      |        |                              |              |                          |           |
| 1W6  | 6      | 1W6                          | 3.50         | 4.472222                 | 0.972222  |
| 2W3  | 6      | 2W6 (halbiert, aufgerundet)  | 4.00         | 4.666667                 | 0.666667  |
| 3W2  | 6      | 3W4 (halbiert, aufgerundet)  | 4.50         | 4.9375                   | 0.4375    |
|      |        |                              |              |                          |           |
| 1W8  | 8      | 1W8                          | 4.50         | 5.8125                   | 1.3125    |
| 2W4  | 8      | 2W4                          | 5.00         | 5.9375                   | 0.9375    |
| 4W2  | 8      | 4W4 (halbiert, aufgerundet)  | 6.00         | 6.46875                  | 0.46875   |
|      |        |                              |              |                          |           |
| 3W3  | 9      | 3W6 (halbiert, aufgerundet)  | 6.00         | 6.790123                 | 0.790123  |
|      |        |                              |              |                          |           |
| 1W10 | 10     | 1W10                         | 5.50         | 7.15                     | 1.65      |
| 2W5  | 10     | 2W10 (halbiert, aufgerundet) | 6.00         | 7.2                      | 1.2       |
| 5W2  | 10     | 5W4 (halbiert, aufgerundet)  | 7.50         | 7.984375                 | 0.484375  |
|      |        |                              |              |                          |           |
| 1W12 | 12     | 1W12                         | 6.50         | 8.486111                 | 1.986111  |
| 2W6  | 12     | 2W6                          | 7.00         | 8.458333                 | 1.458333  |
| 3W4  | 12     | 3W4                          | 7.50         | 8.617188                 | 1.117188  |
| 4W3  | 12     | 4W6 (halbiert, aufgerundet)  | 8.00         | 8.864198                 | 0.864198  |
| 6W2  | 12     | 6W4 (halbiert, aufgerundet)  | 9.00         | 9.492188                 | 0.492188  |
|      |        |                              |              |                          |           |
| 7W2  | 14     | 7W4 (halbiert, aufgerundet)  | 10.50        | 10.996094                | 0.496094  |
|      |        |                              |              |                          |           |
| 3W5  | 15     | 3W10 (halbiert, aufgerundet) | 9.00         | 10.4336                  | 1.4336    |
| 5W3  | 15     | 5W6 (halbiert, aufgerundet)  | 10.00        | 10.910837                | 0.910837  |
|      |        |                              |              |                          |           |
| 2W8  | 16     | 2W8                          | 9.00         | 10.96875                 | 1.96875   |
| 4W4  | 16     | 4W4                          | 10.00        | 11.230469                | 1.230469  |
| 8W2  | 16     | 8W4 (halbiert, aufgerundet)  | 12.00        | 12.498047                | 0.498047  |
|      |        |                              |              |                          |           |
| 3W6  | 18     | 3W6                          | 10.50        | 12.244599                | 1.744599  |
| 6W3  | 18     | 6W6 (halbiert, aufgerundet)  | 12.00        | 12.941015                | 0.941015  |
| 9W2  | 18     | 9W4 (halbiert, aufgerundet)  | 13.50        | 13.999023                | 0.499023  |
|      |        |                              |              |                          |           |
| 1W20 | 20     | 1W20                         | 10.50        | 13.825                   | 3.325     |
| 2W10 | 20     | 2W10                         | 11.00        | 13.475                   | 2.475     |
| 4W5  | 20     | 4W10 (halbiert, aufgerundet) | 12.00        | 13.584                   | 1.584     |
| 5W4  | 20     | 5W4                          | 12.50        | 13.806152                | 1.306152  |
| 10W2 | 20     | 10W4 (halbiert, aufgerundet) | 15.00        | 15.499512                | 0.499512  |