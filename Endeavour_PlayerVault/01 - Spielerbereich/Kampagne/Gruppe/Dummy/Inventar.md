---
Charakter: "[[Dummy]]"
endeavour_inventory:
  containers:
    - container: "[[Rucksack (Groß)]]"
      items:
        - "[[Schaufel]]"
        - "[[Blendlaterne]]"
        - name: Platzhalter Schwert
          plaetze: 2
        - name: Seltsamer Schlüssel
          plaetze: 1
    - container: "[[Gürteltasche]]"
      items:
        - "[[Köcher]]"
    - container: "[[Gürteltasche]]"
      items: []
currency: { cp: 12, sp: 8, ep: 0, gp: 30, pp: 1 }
---

Inventar zu [[Dummy]]. `Platzhalter Schwert` und `Seltsamer Schlüssel` sind bewusst als temporäre
Gegenstände (`name`+`plaetze`, ohne eigene Vault-Seite) eingetragen — das deckt den entsprechenden
Fallback-Pfad der App-Inventar-UI mit ab. Das Zelt (`Items/Zelt.md`) ist bewusst nicht vorplatziert,
sondern nur über die Suche zu finden — es passt wegen `Plaetze: 4` ("Sehr Groß") nicht in den
Rucksack (`MaxGroesse: Groß`), gut zum Live-Testen der Größenprüfung.
