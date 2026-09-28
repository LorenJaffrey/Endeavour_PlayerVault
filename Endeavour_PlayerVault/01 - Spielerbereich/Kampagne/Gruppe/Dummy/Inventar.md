---
Charakter: "[[Dummy]]"
endeavour_inventory:
  containers:
    - container: '[[Rucksack (Groß)]]'
      items:
        - '[[Kampfstab]]'
        - '[[Ration]]'
        - '[[Ration]]'
        - '[[Ration]]'
        - '[[Ration]]'
        - '[[Ration]]'
        - name: Seife
          plaetze: 1
        - name: Zauberbuch
          plaetze: 1
        - link: '[[Fackel]]'
          charges: 2
        - '[[Blendlaterne]]'
        - '[[Einfacher Rum (Flasche)]]'
    - container: '[[Gürteltasche]]'
      items:
        - '[[Dolch]]'
    - container: '[[Gürteltasche]]'
      items:
        - name: Seltsamer Schlüssel
          plaetze: 1
currency: {cp: 73, sp: 24, ep: 0, gp: 15, pp: 4}
---

Inventar zu [[Dummy]], aufgebaut aus der Startausrüstung des [[Arkanist|Arkanisten]] ([[Kampfstab]],
Robe, 5 [[Ration|Rationen]], Seife, 15 GM) plus ein paar Fundstücken aus bisherigen Abenteuern. Die Robe
wird getragen und belegt keinen Platz. `Seife`, `Zauberbuch` und `Seltsamer Schlüssel` haben (noch) keine
eigene Vault-Seite und sind bewusst als temporäre Gegenstände (`name`+`plaetze`) eingetragen, das deckt
den entsprechenden Fallback-Pfad der App-Inventar-UI mit ab; alle anderen sind reale Einträge aus dem
zentralen `01 - Spielerbereich/Gegenstände/`-Ordner. Der Rucksack ist mit 13 von 15 Plätzen gut gefüllt. Das Zelt
(`Gegenstände/Ausrüstung/Zelt.md`) ist bewusst nicht vorplatziert, sondern nur über die Suche zu
finden — es passt wegen `Plaetze: 4` ("Sehr Groß") nicht in den Rucksack (`MaxGroesse: Groß`), gut
zum Live-Testen der Größenprüfung.
