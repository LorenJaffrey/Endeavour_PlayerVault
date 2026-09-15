> [!column | 2 no-title]
>> ```dataviewjs
>> const currentPage = dv.current();
>> const labels = ["Donnerschlag", "Kältestrahl", "Klingenbann", "Schockgriff", "Windbö", "Chaospfeil", "Hexenpfeil", "Magierrüstung", "Schutzwind", "Snillocs Schneeballschwarm"];
>> const data = [currentPage.ZauberStatistik.Donnerschlag, currentPage.ZauberStatistik.Kältestrahl, currentPage.ZauberStatistik.Klingenbann, currentPage.ZauberStatistik.Schockgriff, currentPage.ZauberStatistik.Windbö, currentPage.ZauberStatistik.Chaospfeil, currentPage.ZauberStatistik.Hexenpfeil, currentPage.ZauberStatistik.Magierrüstung, currentPage.ZauberStatistik.Schutzwind, currentPage.ZauberStatistik.Snillocs_Schneeballschwarm];
>> 
>> const chartData = {  
>>     type: 'line',
>>     data: {
>>         labels: labels,
>>         datasets: [{
>>             label: 'Zauber Anwendungen',
>>             data: data,
>>             backgroundColor: [ 'rgb(136, 192, 208)' ],
>>             borderColor: [ 'rgb(136, 192, 208)' ],
>>             pointStyle: 'circle',
>>             pointRadius: 10,
>> 		    pointHoverRadius: 15
>>         }]
>>     },
>>     options: {
>> 	    indexAxis: 'y',
>> 	    scales: {
>> 		  min: 0,
>> 		  max: 100,		  
>> 	      x: {
>> 	        beginAtZero: true
>> 	      }
>> 	    }
>> 	}
>> }
>> 
>> window.renderChart(chartData, this.container);
>> ```
>
>> |                     Verwendungen                     | Zauber                         |             +              |              -               |
>> |:----------------------------------------------------:|:------------------------------ |:--------------------------:|:----------------------------:|
>> |        `VIEW[{ZauberStatistik.Donnerschlag}]`        | [[Donnerschlag]]               | `BUTTON[donnerschlag_up]`  | `BUTTON[donnerschlag_down]`  |
>> |        `VIEW[{ZauberStatistik.Kältestrahl}]`         | [[Kältestrahl]]                |  `BUTTON[kältestrahl_up]`  |  `BUTTON[kältestrahl_down]`  |
>> |        `VIEW[{ZauberStatistik.Klingenbann}]`         | [[Klingenbann]]                |  `BUTTON[klingenbann_up]`  |  `BUTTON[klingenbann_down]`  |
>> |        `VIEW[{ZauberStatistik.Schockgriff}]`         | [[Schockgriff]]                |  `BUTTON[schockgriff_up]`  |  `BUTTON[schockgriff_down]`  |
>> |           `VIEW[{ZauberStatistik.Windbö}]`           | [[Windbö]]                     |    `BUTTON[windbö_up]`     |    `BUTTON[windbö_down]`     |
>> |         `VIEW[{ZauberStatistik.Chaospfeil}]`         | [[Chaospfeil]]                 |  `BUTTON[chaospfeil_up]`   |  `BUTTON[chaospfeil_down]`   |
>> |         `VIEW[{ZauberStatistik.Hexenpfeil}]`         | [[Hexenpfeil]]                 |  `BUTTON[hexenpfeil_up]`   |  `BUTTON[hexenpfeil_down]`   |
>> |       `VIEW[{ZauberStatistik.Magierrüstung}]`        | [[Magierrüstung]]              | `BUTTON[magierrüstung_up]` | `BUTTON[magierrüstung_down]` |
>> |         `VIEW[{ZauberStatistik.Schutzwind}]`         | [[Schutzwind]]                 |  `BUTTON[schutzwind_up]`   |  `BUTTON[schutzwind_down]`   |
>> | `VIEW[{ZauberStatistik.Snillocs_Schneeballschwarm}]` | [[Snillocs Schneeballschwarm]] |   `BUTTON[snillocs_up]`    |   `BUTTON[snillocs_down]`    | 
>>

```meta-bind-button
 icon: up-arrow-with-tail
 label: ""
 hidden: true
 class: ""
 tooltip: ""
 id: "donnerschlag_up"
 style: primary
 actions:
   - type: updateMetadata
     bindTarget: ZauberStatistik.Donnerschlag
     evaluate: true
     value: x + 1
```

 ```meta-bind-button
 icon: down-arrow-with-tail
 label: ""
 hidden: true
 class: ""
 tooltip: ""
 id: "donnerschlag_down"
 style: primary
 actions:
   - type: updateMetadata
     bindTarget: ZauberStatistik.Donnerschlag
     evaluate: true
     value: x - 1
 
 ```

```meta-bind-button
 label: ""
 icon: up-arrow-with-tail
 hidden: true
 class: ""
 tooltip: ""
 id: "kältestrahl_up"
 style: primary
 actions:
    - type: updateMetadata
      bindTarget: ZauberStatistik.Kältestrahl
      evaluate: true
      value: x + 1
 
```

 ```meta-bind-button
 label: ""
 icon: down-arrow-with-tail
 hidden: true
 class: ""
 tooltip: ""
 id: "kältestrahl_down"
 style: primary
 actions:
   - type: updateMetadata
     bindTarget: ZauberStatistik.Kältestrahl
     evaluate: true
     value: x - 1
 
 ```

 ```meta-bind-button
 label: ""
 icon: up-arrow-with-tail
 hidden: true
 class: ""
 tooltip: ""
 id: "klingenbann_up"
 style: primary
 actions:
    - type: updateMetadata
      bindTarget: ZauberStatistik.Klingenbann
      evaluate: true
      value: x + 1
 
 ```

 ```meta-bind-button
 label: ""
 icon: down-arrow-with-tail
 hidden: true
 class: ""
 tooltip: ""
 id: "klingenbann_down"
 style: primary
 actions:
   - type: updateMetadata
     bindTarget: ZauberStatistik.Klingenbann
     evaluate: true
     value: x - 1
 
 ```

 ```meta-bind-button
 label: ""
 icon: up-arrow-with-tail
 hidden: true
 class: ""
 tooltip: ""
 id: "schockgriff_up"
 style: primary
 actions:
    - type: updateMetadata
      bindTarget: ZauberStatistik.Schockgriff
      evaluate: true
      value: x + 1
 
 ```
 
```meta-bind-button
label: ""
icon: down-arrow-with-tail
hidden: true
class: ""
tooltip: ""
id: "schockgriff_down"
style: primary
actions:
  - type: updateMetadata
    bindTarget: ZauberStatistik.Schockgriff
    evaluate: true
    value: x - 1

```

```meta-bind-button
 label: ""
 icon: up-arrow-with-tail
 hidden: true
 class: ""
 tooltip: ""
 id: "windbö_up"
 style: primary
 actions:
   - type: updateMetadata
     bindTarget: ZauberStatistik.Windbö
     evaluate: true
     value: x + 1

```

```meta-bind-button
label: ""
icon: down-arrow-with-tail
hidden: true
class: ""
tooltip: ""
id: "windbö_down"
style: primary
actions:
  - type: updateMetadata
    bindTarget: ZauberStatistik.Windbö
    evaluate: true
    value: x - 1

```

```meta-bind-button
 label: ""
 icon: up-arrow-with-tail
 hidden: true
 class: ""
 tooltip: ""
 id: "chaospfeil_up"
 style: primary
 actions:
   - type: updateMetadata
     bindTarget: ZauberStatistik.Chaospfeil
     evaluate: true
     value: x + 1

```

```meta-bind-button
label: ""
icon: down-arrow-with-tail
hidden: true
class: ""
tooltip: ""
id: "chaospfeil_down"
style: primary
actions:
  - type: updateMetadata
    bindTarget: ZauberStatistik.Chaospfeil
    evaluate: true
    value: x - 1

```

```meta-bind-button
 label: ""
 icon: up-arrow-with-tail
 hidden: true
 class: ""
 tooltip: ""
 id: "hexenpfeil_up"
 style: primary
 actions:
   - type: updateMetadata
     bindTarget: ZauberStatistik.Hexenpfeil
     evaluate: true
     value: x + 1

```

```meta-bind-button
label: ""
icon: down-arrow-with-tail
hidden: true
class: ""
tooltip: ""
id: "hexenpfeil_down"
style: primary
actions:
  - type: updateMetadata
    bindTarget: ZauberStatistik.Hexenpfeil
    evaluate: true
    value: x - 1

```

```meta-bind-button
 label: ""
 icon: up-arrow-with-tail
 hidden: true
 class: ""
 tooltip: ""
 id: "magierrüstung_up"
 style: primary
 actions:
   - type: updateMetadata
     bindTarget: ZauberStatistik.Magierrüstung
     evaluate: true
     value: x + 1

```

```meta-bind-button
label: ""
icon: down-arrow-with-tail
hidden: true
class: ""
tooltip: ""
id: "magierrüstung_down"
style: primary
actions:
  - type: updateMetadata
    bindTarget: ZauberStatistik.Magierrüstung
    evaluate: true
    value: x - 1

```

```meta-bind-button
 label: ""
 icon: up-arrow-with-tail
 hidden: true
 class: ""
 tooltip: ""
 id: "schutzwind_up"
 style: primary
 actions:
   - type: updateMetadata
     bindTarget: ZauberStatistik.Schutzwind
     evaluate: true
     value: x + 1

```

```meta-bind-button
label: ""
icon: down-arrow-with-tail
hidden: true
class: ""
tooltip: ""
id: "schutzwind_down"
style: primary
actions:
  - type: updateMetadata
    bindTarget: ZauberStatistik.Schutzwind
    evaluate: true
    value: x - 1

```

```meta-bind-button
 label: ""
 icon: up-arrow-with-tail
 hidden: true
 class: ""
 tooltip: ""
 id: "snillocs_up"
 style: primary
 actions:
   - type: updateMetadata
     bindTarget: ZauberStatistik.Snillocs_Schneeballschwarm
     evaluate: true
     value: x + 1
```

```meta-bind-button
label: ""
icon: down-arrow-with-tail
hidden: true
class: ""
tooltip: ""
id: "snillocs_down"
style: primary
actions:
  - type: updateMetadata
    bindTarget: ZauberStatistik.Snillocs_Schneeballschwarm
    evaluate: true
    value: x - 1
```
