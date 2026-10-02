# Anleitung: Neuer Charakter

Diese Anleitung zeigt, wie aus den Vorlagen in diesem Ordner der Charakterbogen eines Gruppenmitglieds
wird — so, dass er in Obsidian *und* in der D&D-Companion-App funktioniert. Ein vollständig ausgefülltes
Beispiel ist [[Dummy]] unter `Gruppe/Dummy/`.

> [!info] Vorlagen in diesem Ordner
> - [[Vorlage Charakter]] — der Charakterbogen (Pflicht)
> - [[Vorlage Inventar]] — Inventar und Geld (Pflicht)
> - [[Vorlage Spell Sheet]] — Mana und bekannte Zauber (nur Zauberwirker)
>
> Alles mit „Vorlage“ im Pfad ignoriert die App — die Vorlagen tauchen dort nie als Charakter auf.

---

## 1. Ordnerstruktur

Jeder Charakter bekommt einen eigenen Ordner unter `Kampagne/Gruppe/`, benannt nach seinem Dateinamen:

```
Kampagne/Gruppe/
├── Gruppe.md
├── _Vorlage Charakter/              ← diese Vorlagen (nicht verschieben)
└── Borin Eisenfaust/                ← ein Ordner pro Charakter
    ├── Borin Eisenfaust.md          ← Charakterbogen
    ├── Inventar Borin Eisenfaust.md
    ├── Spell Sheet Borin Eisenfaust.md   ← nur Zauberwirker
    ├── Spells/                      ← eigene Zaubernotizen (bis es eine zentrale Zauberliste gibt)
    │   └── Funkenschlag.md
    └── _Attachments/
        └── Borin Eisenfaust Portrait.jpg
```

## 2. Namensregeln

| Was | Name | Beispiel |
|---|---|---|
| Ordner | `<Charaktername>` | `Borin Eisenfaust` |
| Charakterbogen | `<Charaktername>.md` | `Borin Eisenfaust.md` |
| Inventar | `Inventar <Charaktername>.md` | `Inventar Borin Eisenfaust.md` |
| Spell Sheet | `Spell Sheet <Charaktername>.md` | `Spell Sheet Borin Eisenfaust.md` |
| Portrait | `<Charaktername> Portrait.<jpg/png/webp>` | `Borin Eisenfaust Portrait.jpg` |
| Zauber | `<Zaubername>.md` | `Funkenschlag.md` |

**Warum so:**
- Obsidian verlinkt über den Dateinamen. Hieße jedes Inventar nur `Inventar.md`, wäre `[[Inventar]]`
  mehrdeutig. Deshalb bekommt jede Begleitnotiz den Charakternamen. (Der [[Dummy]] nutzt als
  Entwicklungs-Platzhalter noch die kurzen Namen — für echte Charaktere bitte nicht nachmachen.)
- Inventar und Spell Sheet werden über `Charakter: "[[<Charaktername>]]"` dem Charakter zugeordnet —
  dort steht der **Dateiname** des Charakterbogens, nicht der Anzeigename.
- Keine Zeichen verwenden, die Obsidian in Dateinamen nicht mag: `/ \ : # ^ [ ] |`.
- Der Anzeigename (`name:` im Bogen) darf abweichen, z. B. `Borin „Steinherz“ Eisenfaust`.

## 3. Schritt für Schritt

- [ ] Ordner `Kampagne/Gruppe/<Charaktername>/` anlegen, darin `_Attachments/` (und `Spells/` für Zauberwirker)
- [ ] [[Vorlage Charakter]] hineinkopieren und in `<Charaktername>.md` umbenennen
- [ ] [[Vorlage Inventar]] hineinkopieren → `Inventar <Charaktername>.md`
- [ ] Zauberwirker: [[Vorlage Spell Sheet]] hineinkopieren → `Spell Sheet <Charaktername>.md`
- [ ] In **allen** kopierten Dateien `CHARNAME` durch den Dateinamen ersetzen (Strg+H, „Alle ersetzen“)
- [ ] Portrait nach `_Attachments/<Charaktername> Portrait.jpg` legen
- [ ] Im Bogen `tags: [Charakter/GORN]` setzen, damit er in [[Gruppe]] erscheint
- [ ] Felder ausfüllen (Abschnitt 4) — die Kommentare `# …` im Frontmatter erklären jedes Feld
- [ ] Kein Zauberwirker: im Bogen den Abschnitt „✨ Magie“ löschen
- [ ] Optional die Kommentare im Frontmatter entfernen, sobald alles stimmt
- [ ] Prüfen (Abschnitt 7)

## 4. Was eingetragen wird

### Charakterbogen

| Feld | Pflicht | Inhalt |
|---|:---:|---|
| `type` | ✔ | immer `character` — daran erkennt die App den Bogen |
| `name` | ✔ | Anzeigename |
| `portrait` | | `"[[<Charaktername> Portrait.jpg]]"` |
| `class` | ✔ | Liste aus `name` (exakt wie die Notiz unter `Charaktere/Klassen/`), `level`, optional `subclass`; Multiclass = mehrere Einträge, Startklasse zuerst |
| `species`, `background`, `alignment` | ✔ | Spezies, Hintergrund, Gesinnung als Text |
| `experience` | | Erfahrungspunkte |
| `nimble_attributes` | ✔ | die acht Attribute `st bw ko ge in vs pr en`, je −5 … +5 |
| `nimble_skills` | | nur trainierte Fertigkeiten, je 0 … +10 (Schlüssel siehe unten) |
| `abilities` | | Brücke für Zauber-SG/-Angriff: je 10 + 2 × Attribut (st→str, bw→dex, ko→con, vs→int, in→wis, pr→cha) |
| `armor` | | getragene Rüstung als Link, z. B. `"[[Lederrüstung]]"` — leer = keine |
| `shield` | | Schild als Link |
| `attacks` | | Waffen als Links, z. B. `- "[[Dolch]]"` |
| `speed` | ✔ | z. B. `30 ft` (= 6 Felder) |
| `hp`, `resilience` | ✔ | `current` und `max` (und `temp` bei hp) |
| `conditions.exhaustion` | | Erschöpfung 0 … 6, optional `notes` |
| `senses`, `languages` | | z. B. `{ darkvision: 18 m }`, `[Gemeinsprache, Zwergisch]` |
| `Merkmale` | | Links auf Notizen mit Tag `#Merkmal` (z. B. `[[Dunkelsicht]]`); deren `Einsatz` entscheidet Aktion/Reaktion/Passiv |
| `formation` | | `vorne`/`mitte`/`hinten` — überschreibt die Klasse in der Gruppenaufstellung der App |
| `backstory` | | Vorgeschichte, mehrere Absätze |
| `Persönlichkeit` | | `Persönlichkeitsmerkmale` (Liste), `Ideale`, `Bindungen`, `Makel` — oder ein einfacher Text |
| `Aussehen` | | `Geschlecht`, `Alter`, `Größenkategorie`, `Größe`, `Gewicht`, `Augenfarbe`, `Haarfarbe`, `Hautfarbe` (eigene Felder erlaubt) — oder ein einfacher Text |

**Rechnet die App selbst — nur für Obsidian mitpflegen:**
- `hp.max` und `resilience.max` aus `BasisTP`/`BasisRP` der Klassennotiz: (Stufe + 1) × (BasisTP + KO) bzw. (Stufe + 1) × (BasisRP + EN/2)
- `armor_class` und Max BW aus der verlinkten Rüstung
- Angriffsbonus und Schaden aus den Waffennotizen und ST/GE
- Kernattribute sowie Vorteil/Nachteil auf Rettungswürfe aus der Klassennotiz

**Bleibt leer:** `saving_throw_proficiencies: []` und `skill_proficiencies: []` (D&D-Felder, Endeavour nutzt Klassennotiz und `nimble_skills`).

### Fertigkeitsschlüssel für `nimble_skills`

| Schlüssel | Fertigkeit | Attr. | | Schlüssel | Fertigkeit | Attr. |
|---|---|:-:|---|---|---|:-:|
| `athletics` | Athletik | ST | | `animal_handling` | Tierführung | IN |
| `acrobatics` | Akrobatik | BW | | `insight` | Einsicht | IN |
| `sleight_of_hand` | Fingerfertigkeit | GE | | `perception` | Wahrnehmung | IN |
| `stealth` | Heimlichkeit | GE | | `survival` | Überlebenskunst | IN |
| `arcana` | Magiekunde | VS | | `deception` | Täuschung | PR |
| `history` | Geschichte | VS | | `intimidation` | Einschüchterung | PR |
| `investigation` | Nachforschung | VS | | `performance` | Auftreten | PR |
| `nature` | Naturkunde | VS | | `persuasion` | Überzeugung | PR |
| `religion` | Religion | VS | | | | |
| `medicine` | Heilkunde | VS | | | | |

### Inventar und Spell Sheet

Die Kommentare in [[Vorlage Inventar]] und [[Vorlage Spell Sheet]] erklären jedes Feld. Kurz:
- **Inventar:** Behälter (`container`) mit ihren Gegenständen, alles als Links auf `Gegenstände/`. Was keine
  eigene Notiz hat, wird als `name` + `plaetze` eingetragen. Dazu das Geld in `currency`.
- **Spell Sheet:** Mana (`current`/`max`), höchster freigeschalteter Grad (`max_tier`) und die bekannten
  Zauber als Links.

### Zaubernotiz (unter `Spells/`)

```yaml
---
type: spell
name: Funkenschlag
level: 1              # Grad, 0 = Zaubertrick
school: Feuer
casting_time: 1 Aktion
actions: 2            # Aktionspunkte
range: 18 m
components: [V, S]
duration: Sofort
classes: [Arkanist]
target_kind: single   # single | aoe | self | special
damage: 1d10
damage_type: Feuerschaden
save_ability: dex     # optional: Rettungswurf statt Angriff
upcast: +1d10 Schaden # optional: Text zum Hochstufen
---
Beschreibung des Zaubers.
```

Weitere Beispiele: `Gruppe/Dummy/Spells/`.

## 5. Bezüge zum Regelwerk

- Klassen: `Charaktere/Klassen/<Klasse>/<Klasse>.md` — Name muss exakt zu `class.name` passen
- Gegenstände, Waffen, Rüstungen, Behälter: `01 - Spielerbereich/Gegenstände/`
- Merkmale: alle Notizen mit Tag `#Merkmal`, Übersicht in [[Merkmale]]
- Attribute, Fertigkeiten, Rettungswürfe: `Regeln/Allgemein/`

## 6. Noch offen im Regelwerk

Das System ist im Aufbau. Diese Punkte betreffen die Bögen und sollten mitgezogen werden, sobald sie
entschieden sind:
- **Spezies:** Es gibt noch keine Spezies-Notizen — `species` ist bisher reiner Text.
- **Zauber:** Es gibt noch keine zentrale Zauberliste — Zauber liegen pro Charakter unter `Spells/`.
- **Hintergrund:** Ob es eigene Hintergrund-Notizen gibt oder ein vereinfachtes System, ist offen.
  `background` ist bisher reiner Text, die Biografie-Felder sind alle optional.
- **Subklassen und Multiclassing:** Die TP/RP-Regeln dafür sind in der App vorläufig.
- **Zauber-SG/-Angriff** laufen noch über die `abilities`-Brücke.
- **[[Gruppe]]** liest in ihrer Tabelle noch die alten Felder (`Hintergrund.Volk`, `Hintergrund.Klasse`)
  — für die neuen Bögen auf `species`, `class` usw. umstellen.

## 7. Prüfen

- **Obsidian:** Bogen öffnen. Alle Tabellen müssen Werte zeigen, Links dürfen nicht ins Leere zeigen
  (keine lila/„nicht erstellt“-Links bei Klasse, Waffen, Rüstung, Inventar, Spell Sheet).
- **App:** Vault in der Companion-App öffnen. Der Charakter erscheint in der Übersicht. Im Bogen
  stimmen TP/RP-Maximum, RK, Angriffe und Fertigkeiten. Inventar und (falls vorhanden) Zauber-Tab
  sind gefüllt, im Tab „Biografie“ steht die Vorgeschichte.

---

## Prompt für Claude

Statt alles von Hand auszufüllen, kann Claude (z. B. Claude Code im Vault-Ordner) den Bogen anlegen.
Den Block kopieren, die Angaben unten ergänzen und abschicken:

````text
Lege in meinem Obsidian-Vault einen neuen Spielercharakter an. Halte dich genau an
"01 - Spielerbereich/Kampagne/Gruppe/_Vorlage Charakter/Anleitung Neuer Charakter.md"
und nutze die Vorlagen im selben Ordner. Als ausgefülltes Beispiel dient Gruppe/Dummy/.

Vorgehen:
1. Lies die Anleitung, die drei Vorlagen und die Klassennotiz unter Charaktere/Klassen/<Klasse>/.
2. Lege Ordner und Dateien nach der Ordnerstruktur und den Namensregeln an und ersetze CHARNAME
   überall durch den Dateinamen.
3. Fülle das Frontmatter aus meinen Angaben. Rechne hp.max und resilience.max mit BasisTP/BasisRP
   der Klassennotiz, abilities als 10 + 2 × Attribut. Verlinke nur Gegenstände, Waffen, Rüstungen
   und Merkmale, die es im Vault wirklich gibt; was fehlt, trägst du im Inventar als name + plaetze
   ein und listest es mir am Ende auf.
4. Kein Zauberwirker: kein Spell Sheet und den Abschnitt „✨ Magie“ im Bogen löschen.
5. Erfinde keine Regelwerte. Wo eine Angabe fehlt, lass den Vorlagenwert stehen und sag mir, was offen ist.
6. Zeig mir am Ende die angelegten Dateien und eine Liste offener Punkte. Nicht committen.

Charakter:
- Name / Dateiname:
- Klasse und Stufe (ggf. Subklasse):
- Spezies, Hintergrund, Gesinnung:
- Attribute (ST BW KO GE IN VS PR EN):
- Trainierte Fertigkeiten mit Wert:
- Rüstung, Schild, Waffen:
- Inventar und Geld:
- Zauber (nur Zauberwirker):
- Sinne, Sprachen, Merkmale:
- Vorgeschichte, Persönlichkeit, Aussehen (Stichpunkte reichen):
- Portrait-Datei (falls vorhanden):
````
