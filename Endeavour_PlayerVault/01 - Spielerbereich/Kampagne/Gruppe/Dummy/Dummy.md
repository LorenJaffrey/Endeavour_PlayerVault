---
type: character
name: Dummy Charakter
portrait: "[[Dummy Portrait.jpg]]"
backstory: |
  Erschaffen in einem längst verlassenen Alchemielabor — neugierig, gehorsam und erstaunlich zäh für
  seine Größe. Ursprünglich nur gebaut, um Ausrüstung und Zaubersprüche zu testen, hat es inzwischen
  ein gewisses Eigenleben entwickelt: Es sammelt glänzende Kleinteile, nickt Befehlen entschlossen zu,
  bevor es sie erfüllt, und hält sich — allen Warnungen zum Trotz — für unverwundbar, solange sein
  Laborkittel-Fetzen um den Hals hängt.
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
armor: "[[Lederrüstung]]"
speed: 30 ft
hp:
  current: 10
  max: 10
  temp: 10
resilience:
  current: 5
  max: 5
conditions:
  exhaustion: 5
---

![[Dummy Portrait.jpg]]

# Dummy Charakter

#### *Prüfling 1 — Homunkulus — Laborgeschöpf — Wahrhaft Neutral*

> [!quote] Ein kleines Homunkulus-Wesen
> Erschaffen in einem längst verlassenen Alchemielabor — neugierig, gehorsam und erstaunlich zäh für
> seine Größe. Ursprünglich nur gebaut, um Ausrüstung und Zaubersprüche zu testen, hat es inzwischen
> ein gewisses Eigenleben entwickelt: Es sammelt glänzende Kleinteile, nickt Befehlen entschlossen zu,
> bevor es sie erfüllt, und hält sich — allen Warnungen zum Trotz — für unverwundbar, solange sein
> Laborkittel-Fetzen um den Hals hängt.

---

## ⚔️ Vitalwerte

| 🛡️ RK | 💨 Ausweichwert | 🔥 Resilienzpunkte | ❤️ Trefferpunkte | 🏃 Initiative | 👟 Tempo |
|:---:|:---:|:---:|:---:|:---:|:---:|
| **10** | **11** | **5 / 5** | **10 / 10** | **+1** | 30 ft |

*Erfahrung: 0 XP*

## 🎯 Attribute — *Nimble*

| | St | Bw | Ko | Ge | In | Vs | Pr | En |
|---|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| **Wert** | +1 | +1 | +1 | +1 | +1 | +1 | +1 | +1 |

## 🛡️ Rettungswürfe

*(nur die sechs rettungswurf-tragenden Attribute — Ge und In treiben stattdessen Angriffe/Initiative)*

| Stärke | Beweglichkeit | Konstitution | Verstand | Präsenz | Entschlossenheit |
|:--:|:--:|:--:|:--:|:--:|:--:|
| +1 | +1 | +1 | +1 | +1 | +1 |

## 🗡️ Fertigkeiten

| Fertigkeit | Attr. | Bonus |
|---|:--:|:--:|
| Athletik | St | +1 |
| Akrobatik | Bw | +1 |
| Fingerfertigkeit | Ge | +1 |
| Heimlichkeit | Ge | +1 |
| Arkane Kunde | Vs | +1 |
| Geschichte | Vs | +1 |
| Nachforschungen | Vs | +1 |
| Naturkunde | Vs | +1 |
| Religion | Vs | +1 |
| Heilkunde | Vs | +1 |
| Mit Tieren umgehen | In | +1 |
| Motiv erkennen | In | +1 |
| **Wahrnehmung** *(geübt)* | In | **+3** |
| Überlebenskunst | In | +1 |
| Täuschen | Pr | +1 |
| Einschüchtern | Pr | +1 |
| Auftreten | Pr | +1 |
| **Überzeugen** *(geübt)* | Pr | **+2** |

## 👁️ Sinne

| Passive Wahrnehmung |
|:---:|
| **13** |

## 🎒 Ausrüstung & Zauber

- **Rüstung** — [[Lederrüstung]] (Max BW 4 — begrenzt den Ausweichwert erst ab BW +5)
- **Inventar** — [[Inventar]] (Rucksack, Gürteltaschen, Münzen)
- **Zauber** — [[Spell Sheet]] (Zauberplätze + bekannte Zauber: [[Platzhalterfunke]], [[Platzhalterschild]])

---

> [!note]- Technischer Hinweis (Dev-Platzhalter, zum Aufklappen)
> Platzhalter-Charakter für die Entwicklung der Begleit-App, solange dieser Vault noch keine echten
> Spieler-Charakterbögen enthält. Lebt bewusst in einem eigenen Ordner (`Gruppe/Dummy/`) mit allem,
> was zu ihm gehört — Sheet (diese Datei), [[Inventar]] und [[Spell Sheet]] (beide über
> `Charakter: "[[Dummy]]"` verlinkt), Zauberseiten unter `Spells/`, Portrait unter `_Attachments/`.
>
> `nimble_attributes`/`nimble_skills` sind die echten Werte nach den `Regeln/Nimble`-Attributen
> (Stärke/Beweglichkeit/Konstitution/Geschick/Instinkt/Verstand/Präsenz/Entschlossenheit) und
> Fertigkeiten aus dieser Vault — die App zeigt sie an, sobald sie gesetzt sind. `abilities` bleibt
> zusätzlich als interne Brücke stehen (10+2×Attributswert, hier überall 12 ↔ Nimble-Wert 1), damit
> Rüstungsklasse/Initiative/Zauber-SG — die noch nicht auf Nimble umgestellt sind — weiterhin
> plausible Zahlen liefern; sie wird auf dem Bogen selbst nicht mehr angezeigt.
>
> `armor` verlinkt die getragene Rüstung — die App liest deren Max BW (`BW_cap`) für den
> Ausweichwert. Trefferwürfel gibt es nicht mehr: sobald eine Klassennotiz (`Prüfling.md`)
> `TP_pro_Stufe` / `RP_pro_Stufe` angibt, berechnet die App `hp.max` / `resilience.max` selbst
> (Klasse + Subklasse + KO bzw. EN/2 pro Stufe); bis dahin gelten die Werte oben.
