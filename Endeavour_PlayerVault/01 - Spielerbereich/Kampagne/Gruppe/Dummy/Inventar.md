---
Charakter: "[[Dummy]]"
endeavour_inventory:
  containers:
    - container: '[[Rucksack (Groß)]]'
      items:
        - '[[Schaufel]]'
        - name: Seltsamer Schlüssel
          plaetze: 1
        - link: '[[Fackel]]'
          charges: 2
        - '[[Blendlaterne]]'
        - link: '[[Fackel]]'
          charges: 2
    - container: '[[Gürteltasche]]'
      items:
        - '[[Köcher]]'
    - container: '[[Gürteltasche]]'
      items:
        - '[[Kurzschwert]]'
currency: {cp: 73, sp: 24, ep: 0, gp: 15, pp: 4}
---

Inventar zu [[Dummy]]. Alle Gegenstände außer `Seltsamer Schlüssel` sind reale Einträge aus dem
zentralen `01 - Spielerbereich/Gegenstände/`-Ordner — `Seltsamer Schlüssel` bleibt
bewusst als temporärer Gegenstand (`name`+`plaetze`, ohne eigene Vault-Seite) eingetragen, das deckt
den entsprechenden Fallback-Pfad der App-Inventar-UI mit ab. Das Zelt
(`Gegenstände/Ausrüstung/Zelt.md`) ist bewusst nicht vorplatziert, sondern nur über die Suche zu
finden — es passt wegen `Plaetze: 4` ("Sehr Groß") nicht in den Rucksack (`MaxGroesse: Groß`), gut
zum Live-Testen der Größenprüfung.
