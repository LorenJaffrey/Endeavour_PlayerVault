---
# VORLAGE INVENTAR — umbenennen in `Inventar <Charaktername>.md`, CHARNAME ersetzen.
Charakter: "[[CHARNAME]]" # ← Link auf die Charakterdatei (Dateiname!), so findet die App das Inventar
endeavour_inventory:
  containers: # jeder Behälter ist eine Notiz unter `Gegenstände/Behälter/`, seine Plätze stehen dort
    - container: "[[Rucksack (Groß)]]"
      items:
        - "[[Ration]]" # ein Eintrag pro Stück; gleiche Gegenstände stapelt die App selbst
        - "[[Fackel]]"
        # - link: "[[Fackel]]" # mit verbleibenden Ladungen/Anwendungen
        #   charges: 2
        # - name: Seltsamer Schlüssel # Gegenstand ohne eigene Vault-Seite („temporär“)
        #   plaetze: 1
    - container: "[[Gürteltasche]]"
      items: []
currency: { cp: 0, sp: 0, ep: 0, gp: 0, pp: 0 } # Kupfer, Silber, Elektrum, Gold, Platin
---

Inventar zu [[CHARNAME]]. Gegenstände sind Links auf die Notizen unter `01 - Spielerbereich/Gegenstände/`
— Plätze, Größe, Gewicht und Werte kommen von dort, hier steht nur, *was wo* liegt. Getragene Rüstung und
geführte Waffen stehen im Charakterbogen (`armor`, `attacks`) und belegen keine Plätze.

In der Companion-App lässt sich das Inventar per Drag & Drop pflegen; sie schreibt in genau diese Felder
zurück.
