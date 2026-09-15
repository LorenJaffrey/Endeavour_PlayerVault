---
sessionNotes: |
  - Reise nach "Kreis des Donners" (2h)
  - nach einer Stunde von der Reise wurde ein verkohlter Baum gefunden, der 10 Voodoo Puppen hatte
  - Ankunft & Kampf gegen Orks
  -
---
> [!INFO]
> Aktuelle Kampagne -> Woche 4: Tag 22

> [!info | bg-c-plain]-  Woche 1
> ## 🛣️ Tag 1 + 2: Abreise Richtung Phandalin 
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 12hour
>	section G.O.R.N
>		Abreise von Niewinter: milestone, done, a1, 2024-04-23 08:00, 30m
>		Reise auf der Hohen Straße: done, a2, after a1, 2d
>```
>
>## 🗺️ Tag 3: Abenteuerreise auf dem Dreieberpfad: Vom Goblinüberfall bis Phandalin 
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday thursday
>	section G.O.R.N
>		Auf den Dreieberpfad: done, a1, 2024-04-25 07:00, 2h
>		Goblinüberfall: done, milestone, a2, after a1, 30m
>		Cragmaw Versteck: done, a3, after a2, 5h
>		Weiterreise auf dem Dreieberpfad: done, a4, after a3, 3h
>		Herberge an der Weggabelung: done, milestone, a5, after a4, 30m
>		Weiterreise nach Phandalin: done, a6, after a5, 2h
>```
>
>
> ```leaflet
> id: northern_swordcoast_map
> lock: true
> recenter: true
> noScrollZoom: false
> image: [[ice-map-sword-coast-pc.jpg]]
> bounds: [[0,0], [249.2248, 178.816]]
> height: 600px
> width: 50%
> lat: 100
> long: 89.408
> minZoom: 2.5
> maxZoom: 5
> defaultZoom: 2
> zoomDelta: 0.1
> unit: km
> scale: 1
> darkMode: false
> markerTag: 
> - Location/Schwertküste
> ```
>
>
>## ⚔️ Tag 4: Abenteuer in Phandalin: Ankunft, Geschäfte und Konfrontation
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday friday
>	section G.O.R.N
>		Weiterreise nach Phandalin: done, a1, 2024-04-26 07:00, 1.5h
>		Ankunft in Phandalin: done, milestone, a2, after a1, 30m
>		Geschäfte in Phandalin: done, a3, after a2, 6h
>		Rotbrenner aufgemischt: done, milestone, a4, after a3, 30m
>		Lange Rast: done, a5, after a4, 8h
>```
>
>
> ```leaflet
> id: phandalin_map_1
> lock: false
> recenter: true
> noScrollZoom: false
> image: [[phandalin-isometric.jpg]]
> bounds: [[0,0], [131.625, 185.625]]
> height: 800px
> width: 56%
> lat: 100
> long: 89.408
> minZoom: 2.6
> maxZoom: 5
> defaultZoom: 2.6
> zoomDelta: 0.2
> unit: Meter
> scale: 1
> darkMode: false
> markerTag: 
> - Location/Ort/Phandalin
> ```
>
>
>## 🏰 Tag 5: Aufbruch ins Ungewisse: Vom Gasthaus bis zur Zwergenausgrabung
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday saturday
>	section G.O.R.N
>		Überfall auf das Gasthaus: done, milestone, a1, 2024-04-27 02:00, 30m
>		Tresendar Anwesen: done, a2, after a1, 5h
>		Lange Rast: done, a3, after a2, 8h
>		Treffen mit Sildar: done, a4, after a3, 30m
>		Reise zum Haderhügel: done, a5, after a4, 2.5h
>		Kampf mit den Mantikoren: done, milestone, a6, after a5, 30m
>		Kurze Rast: done, a7, after a6, 1h
>		Reise zur Zwergenausgrabung (halber Weg): done, a8, after a7, 4h
>```
>
>## 🩸 Tag 6:  Das verfluchte Zwergenheiligtum: Kämpfe, Fallen und Verluste
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday sunday
>	section G.O.R.N
>		Lager aufgeschlagen: done, milestone, a1, 2024-04-28 00:00, 15m
>		Lange Rast: done, a2, after a1, 8h
>		Lager abgebaut & frühstücken: done, milestone, a3, after a2, 30m
>		Weiterreise zur Zwergenausgrabung: done, a4, after a3, 2h
>		Tempel des bösen Zwergengottes (Zwergenausgrabung) erreicht: done, milestone, a5, after a4, 0m
>		Tempel erkunden: done, a6, after a5, 15m
>		Kampf mit Schleim-Monstern: done, milestone, a7, after a6, 20m
>		Altar untersuchen, Geheimgang gefunden: done, a8, after a7, 30m
>		Verschütteter Durchgang freilegen: done, a9, after a8, 3h
>		Weiter graben (Wahnsinn breitet sich aus): done, a10, after a9, 1h
>		Aranon löst Falle aus: done, milestone, a11, after a10, 10m
>		Raum mit zerstörten Statuen untersuchen: done, a12, after a11, 30m
>		Altarraum nochmal untersuchen: done, a13, after a12, 2h
>		GORN verlässt verfluchten Tempel: milestone, a14, after a13, 0m
>		Ork Überfall/Angriff: milestone, a15, after a14, 15m		
>		Jon Longbow wurde getötet: milestone, a16, after a15, 10m
>		Gruppe hat sich veraztet und die Orks gelootet/verbrannt: done, a17, after a16, 30m
>		Tote Mienenarbeiter Zwerge begraben: done, a18, after a17, 2h
>		Lange Rast: done, a19, after a18, 3h
>```
>
>
> ```leaflet
> id: northern_swordcoast_map_2
> lock: false
> recenter: true
> noScrollZoom: false
> image: [[ice-map-sword-coast-pc.jpg]]
> bounds: [[0,0], [249.2248, 178.816]]
> height: 600px
> width: 50%
> lat: 45
> long: 100
> minZoom: 2.5
> maxZoom: 5
> defaultZoom: 4
> zoomDelta: 0.1
> unit: km
> scale: 1
> darkMode: false
> markerTag: 
> - Location/Schwertküste
> ```
>
>
>## 🍻 Tag 7: Rückkehr nach Phandalin: Belohnungen, Abschiede und neue Bündnisse
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		Lange Rast: a1, 2024-04-29 00:00, 9h 
>		Rückreise nach Phandalin: done, a2, after a1, 9h
>		Ankunft in Phandalin: done, milestone, a3, after a2, 0h
>		Belohnungen von Sildar kassiert: done, milestone, a4, after a3, 30m
>		Lucian lernt [[Ar'go]] in einer Kneipe kennen & tritt G.O.R.N bei: done, milestone, a5, after a3, 30m
>		Ein Bote/Späher erreicht Phandalin: done, milestone, a6, after a5, 20m
>		Gruppe stockt Vorräte auf: done, a7, after a6, 1h
>		Jon bekommt ein Feuerbegräbnis: done, milestone, a8, after a7, 1h
>		After-Party: done, a9, after a8, 190m
>```

> [!info | bg-c-plain]-  Woche 2
>## 🕯️ Tag 8: Dunkle Wege: Nachfeier, Entdeckungen und ein grausames Zeichen
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday tuesday
>	section G.O.R.N
>		After-Party: a1, 2024-04-30 00:00, 4h
>		Schlafen (Kurze/Lange Rast): done, a2, after a1, 3h
>		Reise zur Herberge: done, a3, after a2, 4h
>		Herberge nochmal untersuchen: done, milestone, a4, after a3, 30m
>		Weiterreise (Richtung "Hasenbeere"): done, a5, after a4, 10h
>		Gekreuzigten und gefolteter Mensch an Weggabelung gefunden (Böser Magier "Glasstab"): done, milestone, a6, after a5, 30m
>		Schlafen (Lange Rast): done, a7, after a6, 2h
>```
>## 🛤️ Tag 9: Auf dem Weg nach Hasenbeere: Ruhe und Ausdauer
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday wednesday
>	section G.O.R.N
>		Schlafen (Lange Rast): a1, 2024-05-01 00:00, 7h
>		Weiterreise (Richtung "Hasenbeere"): done, a2, after a1, 12h
>		Schlafen (Lange Rast): done, a3, after a2, 5h
>```
>
>## 🐉 Tag 10: Von Hasenbeere zum Butterschädelhof: Drachenangriff und Befreiung
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday thursday
>	section G.O.R.N
>		Schlafen (Lange Rast): a1, 2024-05-02 00:00, 7h
>		Weiterreise (Richtung "Hasenbeere"): done, a2, after a1, 4h
>		Ankunft "Hasenbeere": done, milestone, a3, after a2, 0m
>		Unterhaltung mit 3 markierten Pferde: done, a4, after a3, 15m
>		Weiterreise (Richtung "Butterschädelhof"): done, a5, after a4, 3h
>		Ankunft "Butterschädelhof": done, milestone, a6, after a5, 0m
>		Erkundung & Schleichen: done, a7, after a6, 30m
>		Niptac befreit "Big Al": done, a8, after a7, 45m
>		Weißer erwachsener Drache überfällt den "Butterschädelhof": done, milestone, a9, after a8, 30m
>		Weißer erwachsener Drache tötet alle Orks und fliegt mit 2 Kühen weg: done, a10, after a9, 30m
>		GORN untersucht die toten Orks & stimmen sich ab: done, milestone, a11, after a10, 1h
>		GORN bringt die Kuh "Petunia" zurück: done, a12, after a11, 2h
>		GORN reist wieder nach Phandalin zurück: done, a13, after a12, 270m
>```
>
>
> ```leaflet
> id: northern_swordcoast_map_3
> lock: false
> recenter: true
> noScrollZoom: false
> image: [[ice-map-sword-coast-pc.jpg]]
> bounds: [[0,0], [249.2248, 178.816]]
> height: 600px
> width: 50%
> lat: 90
> long: 120
> minZoom: 2.5
> maxZoom: 5
> defaultZoom: 3
> zoomDelta: 0.1
> unit: km
> scale: 1
> darkMode: false
> markerTag: 
> - Location/Schwertküste
> ```
>
>
>## 🛏️ Tag 11: Reisen & Schlafen
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday friday
>	section G.O.R.N
>		Reisen - Schlafen (Lange Rast): done a1, 2024-05-03 00:00, 24h
>```
>
>## 🛏️ Tag 12: Reisen & Schlafen
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday saturday
>	section G.O.R.N
>		Reisen - Schlafen (Lange Rast): done a1, 2024-05-04 00:00, 24h
>```
>
>## 🏙️ Tag 13: Ankunft & Abenteuer in Phandalin
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday sunday
>	section G.O.R.N
>		Ankunft in Phandalin: a1, 2024-05-05 00:00, 15h
>		Zildar über den Butterschädelhof und den Weißen Drachen berichtet: done, milestone, a2, after a1, 30m
>		GORN geht mit Sildar saufen: done, a3, after a2, 2h
>		GORN bricht nach Hasenbeere mit der Holzlieferung auf: done, a4, after a3, 7h
>```
>
>## 🛏️ Tag 14: Reisen & Schlafen
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		Reisen - Schlafen (Lange Rast): a1, 2024-05-06 00:00, 24h
>```


> [!info | bg-c-plain]-  Woche 3
>## 🛏️ Tag 15: Reisen & Schlafen
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		Reisen - Schlafen (Lange Rast): a1, 2024-05-07 00:00, 24h
>```
>
>## 🐺 Tag 16: Ankunft & Abenteuer in Hasenbeere
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		Ankunft in Hasenbeere mit der Vorratslieferung: done, milestone, a1, 2024-05-08 00:00, 9h
>		GORN bertitt den Wald Richtung Jagdhaus des Falken: done, a2, after a1, 8h
>		Lange Rast (versuch): done, a3, after a2, 3h
>		Wolfangriff: done, milestone, a4, after a3, 30m
>		Baumel gestorben: done, milestone, a5, after a3, 1h
>		Lange Rast: done, a6, after a4, 4h
>```
>
>## 🌲 Tag 17: Rast, Irrwege & Jagdhaus-Abenteuer
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		Lange Rast: a1, 2024-05-09 00:00, 8h
>		Ochsenkarren gefunden: done, a2, after a1, 1h
>		Verlaufen: done, a3, after a2, 2h
>		Weg wieder gefunden: done, a4, after a3, 2h
>		Verlaufen: done, a5, after a4, 2h
>		Weg wieder gefunden: done, a6, after a5, 2h
>		Jagdhaus des Falken erreicht: done, a7, after a6, 2h	
>		Essen und Übernachtung im Jagdhaus: done, a8, after a7, 5h	
>```
>
>## 🪓 Tag 18: Abenteuer im Holzfällerlager
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		Lange Rast: a1, 2024-05-10 00:00, 8h
>		Reise weiter Richtung Holzfällerlager: done, a2, after a1, 6h
>		Ankunft im Holzfällerlager: done, a3, after a2, 2.5h
>		Überfall durch "Ankheg" Monster: done, milestone, a4, after a3, 0.25h
>		6 Ankheg Monster besiegt: done, a5, after a4, 0.5h
>		Hütte im Holzfällerlager untersucht: done, a6, after a5, 0.25h
>		Weiterer Überfall: done, milestone, a7, after a6, 0.25h
>		2 Ankheg Monster besiegt: done, a8, after a7, 0.25h
>		Tibor Wester gerettet & unterhalten: done, a9, after a8, 0.5h
>		Lager durchsuchen nach Hinweisen: done, a10, after a9, 2h
>		Kurze Rast: done, a11, after a10, 1h
>		Lange Rast: done, a12, after a11, 2.5h
>```
>
>## 🦅 Tag 19: Reise zum Jagdhaus des Falken
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		Lange Rast: a1, 2024-05-11 00:00, 8h
>		Reise zum Jagdhaus des Falken: done, a2, after a1, 16h
>```
>
>
> ```leaflet
> id: northern_swordcoast_map_4
> lock: false
> recenter: true
> noScrollZoom: false
> image: [[ice-map-sword-coast-pc.jpg]]
> bounds: [[0,0], [249.2248, 178.816]]
> height: 600px
> width: 50%
> lat: 100
> long: 89.408
> minZoom: 2.5
> maxZoom: 5
> defaultZoom: 2
> zoomDelta: 0.1
> unit: km
> scale: 1
> darkMode: false
> markerTag: 
> - Location/Schwertküste
> ```
>
>
>## 🦅 Tag 20: Ankunft & Rast im Jagdhaus des Falken
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		Reise zum Jagdhaus des Falken: a1, 2024-05-12 00:00, 6h
>		Tibor Wester im Jagdhaus abgeliefert: done, a2, after a1, 2h
>		Im Jagdhaus des Falken rasten: done, a3, after a2, 16h
>```
>
>## ⚔️ Tag 21: Abenteuer im Alten Haus im Wald
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		Lange Rast: a1, 2024-05-13 00:00, 8h
>		Weiterreise Richtung "Altes Haus im Wald" (16 km): done, a2, after a1, 8h
>		Ankunft beim Alten Haus im Wald: done, milestone, a3, after a2, 0h
>		Kampf gegen Mini-GORN Figuren: done, a4, after a3, 0.25h
>		Kampf gegen Blutmücke: done, a5, after a4, 0.25h
>		Kampf gegen Pflanzenwesen im Innenhof: done, a6, after a4, 0.25h
>		 Kampf gegen Orks & Magischen Baum: done, milestone, a7, after a5, 0.25h
>		 Haus Durchsuchung: done, a8, after a7, 1h
>		 Lange Rast: done, a9, after a8, 6.25h
>```
>
>
> ```leaflet
> id: northern_swordcoast_map_5
> lock: false
> recenter: true
> noScrollZoom: false
> image: [[ice-map-sword-coast-pc.jpg]]
> bounds: [[0,0], [249.2248, 178.816]]
> height: 600px
> width: 50%
> lat: 135
> long: 120
> minZoom: 4
> maxZoom: 5
> defaultZoom: 2
> zoomDelta: 0.1
> unit: km
> scale: 1
> darkMode: false
> markerTag: 
> - Location/Schwertküste
> ```
>

> [!info | bg-c-plain]+ Woche 4
>## Tag 22
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		Lange Rast: a1, 2024-05-14 00:00, 8h
>		Haus Durchsuchung: done, a2, after a1, 1h
>```
>
>> [!INFO] 
>> Hier befinden wir uns aktuell! -> Session Notizen:
>>  ```meta-bind
>>  INPUT[editor(class(dndSmallHeight)):sessionNotes]
>>  ```
>
>
>## Tag 23
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		-: a1, 2024-05-15 00:00, 0h
>		
>```
>
>## Tag 24
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		-: a1, 2024-05-16 00:00, 0h
>		
>```
>
>## Tag 25
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		-: a1, 2024-05-17 00:00, 0h
>		
>```
>
>## Tag 26
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		-: a1, 2024-05-18 00:00, 0h
>		
>```
>
>## Tag 27
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		-: a1, 2024-05-19 00:00, 0h
>		
>```
>
>## Tag 28
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		-: a1, 2024-05-20 00:00, 0h
>		
>```

> [!info | bg-c-plain]-  Woche 5
>## Tag 29
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		-: a1, 2024-05-21 00:00, 0h
>		
>```
>
>## Tag 30
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		-: a1, 2024-05-22 00:00, 0h
>		
>```
>
>## Tag 31
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		-: a1, 2024-05-23 00:00, 0h
>		
>```
>
>## Tag 32
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		-: a1, 2024-05-24 00:00, 0h
>		
>```
>
>## Tag 33
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		-: a1, 2024-05-25 00:00, 0h
>		
>```
>
>## Tag 34
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		-: a1, 2024-05-26 00:00, 0h
>		
>```
>
>## Tag 35
>```mermaid
>gantt
>	dateFormat HH:mm
>	axisFormat %e.%m. %H:%M
>	tickinterval 1hour
>	weekday monday
>	section G.O.R.N
>		-: a1, 2024-05-27 00:00, 0h
>		
>```




