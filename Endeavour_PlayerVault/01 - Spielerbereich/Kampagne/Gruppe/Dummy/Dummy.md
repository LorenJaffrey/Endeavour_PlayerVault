---
type: character
name: Dummy Charakter
class:
  - name: Prüfling
    level: 1
species: Homunkulus
background: Laborgeschöpf
alignment: Wahrhaft Neutral
experience: 0
abilities:
  str: 12
  dex: 12
  con: 12
  int: 12
  wis: 12
  cha: 12
proficiency_bonus: 2
saving_throw_proficiencies: []
skill_proficiencies: []
nimble_attributes:
  st: 1
  bw: 1
  ko: 1
  ge: 1
  in: 1
  vs: 1
  pr: 1
  en: 1
nimble_skills:
  perception: 2
  persuasion: 1
armor_class: 10
speed: 30 ft
hp:
  current: 10
  max: 10
hit_dice:
  die: d8
  total: 1
  used: 0
---

*Ein kleines Homunkulus-Wesen, erschaffen in einem längst verlassenen Alchemielabor — neugierig,
gehorsam und erstaunlich zäh für seine Größe. Ursprünglich nur gebaut, um Ausrüstung und Zaubersprüche
zu testen, hat es inzwischen ein gewisses Eigenleben entwickelt.*

Platzhalter-Charakter für die Entwicklung der Begleit-App, solange dieser Vault noch keine echten
Spieler-Charakterbögen enthält. Lebt bewusst in einem eigenen Ordner (`Gruppe/Dummy/`) mit allem, was
zu ihm gehört:

- **Sheet** — diese Datei (Grundwerte)
- **Inventar** — [[Inventar]] (Ausrüstung + Währung, verlinkt über `Charakter: "[[Dummy]]"`)
- **Zauber** — [[Spell Sheet]] (Zauberplätze + bekannte Zauber, gleiche Verlinkung), die
  einzelnen Zauberseiten selbst liegen unter `Spells/`

`Rucksack (Groß)`, `Gürteltasche`, `Blendlaterne`, `Köcher`, `Schaufel` und `Zelt` (unter `Items/`)
sind die realen, vom DM gelieferten Beispiel-Gegenstände (Tags `Gegenstand/Behälter`/
`Gegenstand/Ausrüstung`, Felder `Kosten`/`Plaetze`/`MaxGroesse`/`Stapelgroesse`).

`nimble_attributes`/`nimble_skills` sind die echten Werte nach den `Regeln/Nimble`-Attributen
(Stärke/Beweglichkeit/Konstitution/Geschick/Instinkt/Verstand/Präsenz/Entschlossenheit) und
Fertigkeiten aus dieser Vault — die App zeigt sie an, sobald sie gesetzt sind. `abilities` bleibt
zusätzlich als interne Brücke stehen (10+2×Attributswert, hier überall 12 ↔ Nimble-Wert 1), damit
Rüstungsklasse/Initiative/Zauber-SG — die noch nicht auf Nimble umgestellt sind — weiterhin
plausible Zahlen liefern; sie wird auf dem Bogen selbst nicht mehr angezeigt.
