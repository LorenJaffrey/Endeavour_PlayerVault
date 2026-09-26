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

  Seit es sich der Gruppe angeschlossen hat, trägt es die Spuren mehrerer Abenteuer: eine
  angesengte Stelle am linken Arm (ein Platzhalterfunke, der zu früh gezündet hat), einen
  zerbeulten Rucksack voller Fackelstummel und einen seltsamen Schlüssel, zu dem es noch kein
  Schloss gefunden hat. Seine Aufzeichnungen über jede gewirkte Formel füllen inzwischen ein
  ganzes Notizbüchlein.
class:
  - name: Prüfling
    level: 3
species: Homunkulus
background: Laborgeschöpf
alignment: Wahrhaft Neutral
experience: 1150
abilities:
  str: 8
  dex: 14
  con: 12
  int: 16
  wis: 12
  cha: 8
proficiency_bonus: 2
saving_throw_proficiencies: []
skill_proficiencies: []
nimble_attributes:
  st: -1
  bw: 2
  ko: 1
  ge: 2
  in: 1
  vs: 3
  pr: -1
  en: 2
nimble_skills:
  acrobatics: 1
  sleight_of_hand: 3
  stealth: 2
  arcana: 3
  history: 1
  investigation: 2
  medicine: 1
  perception: 2
  persuasion: 1
armor_class: 2
armor: "[[Lederrüstung]]"
speed: 30 ft
hp:
  current: 14
  max: 21
  temp: 0
resilience:
  current: 7
  max: 12
senses:
  darkvision: 18 m
attacks:
  - name: Kurzschwert
    kind: melee
    attack_bonus: 2
    damage_dice: 1d6
    damage_bonus: 2
    damage_type: Hieb-/Stichschaden
    range: 1,5 m
    properties: [Finesse, Parade, Leicht]
conditions:
  exhaustion: 0
  notes: Angesengter linker Arm aus dem Kampf in der Kanalisation — 1 Erschöpfung, heilt mit der nächsten Sicheren Rast.
---

![[Dummy Portrait.jpg|160]]

# `=this.name`

***`=this.class[0].name` `=this.class[0].level`** · `=this.species` · `=this.background` · `=this.alignment` · `=this.experience` EP*

> [!tip] Charakterbogen nach dem Aufbau des Nimble-Bogens
> Alle Zahlen kommen live aus den Metadaten dieser Notiz, aus [[Spell Sheet]] und [[Inventar]]. Felder mit
> Eingabefeld kannst du direkt hier ändern; sie schreiben in dieselben Metadaten wie die Companion-App.
> Würfel-Knöpfe rechnen die [[Erschöpfung]] (−2 pro Stufe auf W20-Prüfungen) schon ein.

---

## ❤️ Lebenskraft

| ❤️ [[Trefferpunkte\|TP]] | 🔥 [[Resilienzpunkte\|RP]] | 🛡️ [[Temporäre Trefferpunkte\|Temp. TP]] | 🩸 [[Erschöpfung]] |
|:---:|:---:|:---:|:---:|
| `INPUT[number:hp.current]` / `VIEW[{hp.max}]` | `INPUT[number:resilience.current]` / `VIEW[{resilience.max}]` | `INPUT[number:hp.temp]` | `INPUT[inlineSelect(option(0), option(1), option(2), option(3), option(4), option(5), option(6, 6 † tot)):conditions.exhaustion]` / 6 |

*Schaden trifft zuerst temporäre TP, dann RP, zuletzt TP ([[Schaden erleiden]]).*

```dataviewjs
const c = dv.current();
const exh = c.conditions?.exhaustion ?? 0;
const hpPct = Math.round(100 * c.hp.current / c.hp.max);
const rpPct = Math.round(100 * c.resilience.current / c.resilience.max);
const bar = (pct, color) =>
  `<div style="height:8px;border-radius:4px;background:rgba(0,0,0,.35);overflow:hidden">` +
  `<div style="width:${Math.max(0, Math.min(100, pct))}%;height:100%;background:${color}"></div></div>`;
const hpColor = hpPct > 50 ? "#4ade80" : hpPct > 25 ? "#f59e0b" : "#f87171";
dv.el("div", `RP ${bar(rpPct, "#d4af5f")}<br>TP ${bar(hpPct, hpColor)}`);
if (exh > 0) dv.paragraph(`> [!warning] Erschöpfung ${exh}\n> W20-Prüfungen −${2 * exh}, Zauber-SG −${2 * exh}, Bewegung −${1.5 * exh} m.`);
if (c.conditions?.notes) dv.paragraph(`*${c.conditions.notes}*`);
```

## 🧭 Kampfwerte

```dataviewjs
const c = dv.current();
const a = c.nimble_attributes;
const exh = c.conditions?.exhaustion ?? 0;
const fmt = (n) => (n >= 0 ? "+" : "−") + Math.abs(n);
const roll = (n) => `\`dice: 1d20${n - 2 * exh >= 0 ? "+" : ""}${n - 2 * exh}\``;

const armor = c.armor ? dv.page(c.armor.path) : null;
const bwCap = armor?.BW_cap;
const bw = bwCap !== undefined ? Math.min(a.bw, bwCap) : a.bw;
const evasion = 10 + bw;

const feet = Number(String(c.speed).match(/\d+/)?.[0] ?? 0);
const squares = Math.max(0, Math.floor(feet / 5) - exh);
const passive = 10 + a.in + (c.nimble_skills?.perception ?? 0);

dv.table(
  ["🛡️ [[Rüstungsklasse|RK]]", "💨 [[Ausweichwert]]", "⚡ [[Initiative]]", "👟 Bewegung", "👁️ Passive Wahrnehmung", "🎒 Inventarplätze"],
  [[
    `**${c.armor_class}**<br><small>${c.armor ?? "keine Rüstung"}</small>`,
    `**${evasion}**<br><small>10 + BW ${fmt(bw)}${bwCap !== undefined ? ` (max ${bwCap})` : ""}</small>`,
    `Reihenfolge ${roll(a.in)}<br>AP ${roll(a.bw)}`,
    `**${squares} Felder**<br><small>${(squares * 1.5).toLocaleString("de")} m</small>`,
    `**${passive}**`,
    `**${15 + 2 * a.st}**<br><small>15 + St × 2</small>`,
  ]]
);
```

## 🎯 Attribute & Rettungswürfe

```dataviewjs
const c = dv.current();
const a = c.nimble_attributes;
const exh = c.conditions?.exhaustion ?? 0;
const fmt = (n) => (n >= 0 ? "+" : "−") + Math.abs(n);
const roll = (n) => `\`dice: 1d20${n - 2 * exh >= 0 ? "+" : ""}${n - 2 * exh}\``;
const attrs = [
  ["st", "Stärke", true], ["bw", "Beweglichkeit", true], ["ko", "Konstitution", true], ["ge", "Geschick", false],
  ["in", "Instinkt", false], ["vs", "Verstand", true], ["pr", "Präsenz", true], ["en", "Entschlossenheit", true],
];
dv.table(
  ["Attribut", "Wert", "Probe", "Rettungswurf"],
  attrs.map(([k, name, save]) => [`[[${name}]]`, `**${fmt(a[k])}**`, roll(a[k]), save ? roll(a[k]) : "—"])
);
```

*Ge und In haben keinen eigenen Rettungswurf, sie treiben Angriffe bzw. Initiative ([[Rettungswürfe]]).*

## 🗡️ Fertigkeiten

```dataviewjs
const c = dv.current();
const a = c.nimble_attributes;
const s = c.nimble_skills ?? {};
const exh = c.conditions?.exhaustion ?? 0;
const fmt = (n) => (n >= 0 ? "+" : "−") + Math.abs(n);
const roll = (n) => `\`dice: 1d20${n - 2 * exh >= 0 ? "+" : ""}${n - 2 * exh}\``;
const skills = [
  ["athletics", "Athletik", "st"], ["acrobatics", "Akrobatik", "bw"], ["sleight_of_hand", "Fingerfertigkeit", "ge"],
  ["stealth", "Heimlichkeit", "ge"], ["arcana", "Magiekunde", "vs"], ["history", "Geschichte", "vs"],
  ["investigation", "Nachforschung", "vs"], ["nature", "Naturkunde", "vs"], ["religion", "Religion", "vs"],
  ["medicine", "Heilkunde", "vs"], ["animal_handling", "Tierführung", "in"], ["insight", "Einsicht", "in"],
  ["perception", "Wahrnehmung", "in"], ["survival", "Überlebenskunst", "in"], ["deception", "Täuschung", "pr"],
  ["intimidation", "Einschüchterung", "pr"], ["performance", "Auftreten", "pr"], ["persuasion", "Überzeugung", "pr"],
];
dv.table(
  ["Fertigkeit", "Attr.", "Training", "Gesamt", "Wurf"],
  skills.map(([k, name, attr]) => {
    const trained = s[k] ?? 0;
    const total = a[attr] + trained;
    const label = trained > 0 ? `**[[${name}]]**` : `[[${name}]]`;
    return [label, attr.toUpperCase(), trained > 0 ? fmt(trained) : "–", trained > 0 ? `**${fmt(total)}**` : fmt(total), roll(total)];
  })
);
```

*Fertigkeitswurf: W20 + Attributswert + Fertigkeitswert ([[Fertigkeiten]]).*

## ⚔️ Angriffe

```dataviewjs
const c = dv.current();
const exh = c.conditions?.exhaustion ?? 0;
const fmt = (n) => (n >= 0 ? "+" : "−") + Math.abs(n);
const atk = (n) => `\`dice: 1d20${n - 2 * exh >= 0 ? "+" : ""}${n - 2 * exh}\``;
dv.table(
  ["Waffe", "Angriff", "Schaden", "Reichweite", "Eigenschaften"],
  (c.attacks ?? []).map((w) => [
    `[[${w.name}]]`,
    `${fmt(w.attack_bonus)} ${atk(w.attack_bonus)}`,
    `\`dice: ${w.damage_dice}${w.damage_bonus ? fmt(w.damage_bonus).replace("−", "-") : ""}\` ${w.damage_type ?? ""}`,
    w.range,
    (w.properties ?? []).map((p) => `[[${p}]]`).join(", "),
  ])
);
```

*Angriffswurf gegen den [[Ausweichwert]] des Ziels, die [[Rüstungsklasse]] verringert danach den Schaden ([[Angriff]]).*

## ✨ Magie

| 🔮 [[Mana]] | Höchster Grad | Zauberattribut (KEY) | Zauber-SG | Zauberangriff |
|:---:|:---:|:---:|:---:|:---:|
| `INPUT[number:Spell Sheet#spellcasting.mana.current]` / `VIEW[{Spell Sheet#spellcasting.mana.max}]` | `VIEW[{Spell Sheet#spellcasting.max_tier}]` | `$= "VS " + (dv.current().nimble_attributes.vs >= 0 ? "+" : "") + dv.current().nimble_attributes.vs` | `$= 8 + dv.current().proficiency_bonus + Math.floor((dv.current().abilities.int - 10) / 2) - 2 * (dv.current().conditions?.exhaustion ?? 0)` | `$= "+" + (dv.current().proficiency_bonus + Math.floor((dv.current().abilities.int - 10) / 2))` |

*Ein Zauber kostet so viel Mana wie sein Grad, Zaubertricks und Hilfszauber sind kostenlos. Hochstufen bis zum höchsten freigeschalteten Grad kostet den gewählten Grad. Feldrast: halbes Mana zurück, Sichere Rast: alles.*

```dataviewjs
const c = dv.current();
const sheet = dv.page(c.file.folder + "/Spell Sheet");
const key = c.nimble_attributes.vs;
const lvl = c.class.reduce((sum, k) => sum + k.level, 0);
const resolve = (f) =>
  String(f)
    .replace(/KEY\s*([dw]\d+)/gi, (_, d) => `${Math.max(1, key)}${d}`)
    .replace(/\bKEY\b/gi, key).replace(/\bLVL\b/gi, lvl)
    .replace(/\s+/g, "").replace(/\+-/g, "-");
const target = { single: "Einzelziel", aoe: "Fläche", self: "Selbst", special: "Speziell" };
const flow = (s) =>
  s.save_ability ? `DM: ${s.save_ability.toUpperCase()}-RW` :
  s.attack_roll === false || (s.damage && s.target_kind === "aoe") ? "trifft immer" :
  s.damage ? "Angriff" : "—";

const spells = (sheet?.spells_known ?? []).map((l) => dv.page(l.path)).filter(Boolean)
  .sort((x, y) => (x.utility ? 99 : x.level) - (y.utility ? 99 : y.level) || x.name.localeCompare(y.name));

dv.table(
  ["Grad", "Zauber", "Mana", "AP", "Ziel", "Wurf", "Schaden", "Hochstufen"],
  spells.map((s) => [
    s.utility ? "Hilfe" : s.level === 0 ? "Trick" : s.level,
    `${s.file.link}${s.reaction ? " ⚡" : ""}${s.concentration ? " (K)" : ""}`,
    s.utility || s.level === 0 ? "0" : (s.mana_cost ?? s.level),
    s.actions ?? "—",
    target[s.target_kind] ?? s.target ?? "—",
    flow(s),
    s.damage ? `\`dice: ${resolve(s.damage)}\` ${s.damage_type ?? ""}` : "—",
    s.upcast ?? "—",
  ])
);
```

## 🏕️ Rasten

| Rast | Dauer | Erholung |
|---|---|---|
| [[Verschnaufen]] | 10 Min., bis 2×/Tag | 50 % der max. RP |
| [[Feldrast]] | 8 Std. im Lager, 1×/Tag | alle RP, 25 % der max. TP, halbes Mana |
| [[Sichere Rast]] | 8 Std. am sicheren Ort, 1×/Tag | alle RP, 50 % der max. TP, alles Mana, −1 Erschöpfung, temp. TP enden |

## 🎒 Ausrüstung & Sinne

- **Rüstung:** `=this.armor` (RK `=this.armor_class`)
- **Inventar:** [[Inventar]]
- **Zauber:** [[Spell Sheet]]
- **Sinne:** [[Dunkelsicht]] `=this.senses.darkvision`

## 📜 Hintergrund

```dataviewjs
dv.paragraph("> [!quote] " + dv.current().species + "\n> " + String(dv.current().backstory).trim().replace(/\n/g, "\n> "));
```

---

> [!note]- Technischer Hinweis (Dev-Platzhalter, zum Aufklappen)
> Platzhalter-Charakter für die Entwicklung der Begleit-App, solange dieser Vault noch keine echten
> Spieler-Charakterbögen enthält. Lebt bewusst in einem eigenen Ordner (`Gruppe/Dummy/`) mit allem,
> was zu ihm gehört — Sheet (diese Datei), [[Inventar]] und [[Spell Sheet]] (beide über
> `Charakter: "[[Dummy]]"` verlinkt), Zauberseiten unter `Spells/`, Portrait unter `_Attachments/`.
>
> **Der Bogen speichert keine eigenen Zahlen.** Alles oben wird per Dataview aus den Metadaten gelesen
> und per Meta-Bind in dieselben Felder geschrieben, die auch die Companion-App liest und schreibt
> (`hp`, `resilience`, `conditions.exhaustion`, `spellcasting.mana` im Spell Sheet). Benötigt die
> Plugins Dataview (mit aktiviertem JavaScript), Meta Bind und Dice Roller.
>
> `nimble_attributes` (−5…+5) und `nimble_skills` (0…+10, nur trainierte Fertigkeiten) folgen den
> Regeln unter `Regeln/Allgemein/Attribute` bzw. `Fertigkeiten`. `abilities` bleibt als interne
> Brücke stehen (10 + 2 × Attributswert: St→str, Bw→dex, Ko→con, Vs→int, In→wis, Pr→cha), damit
> Zauber-SG und Zauberangriff — die noch nicht auf Nimble umgestellt sind — zu den Attributen passende
> Zahlen liefern.
>
> `armor` verlinkt die getragene Rüstung — Bogen und App lesen deren Max BW (`BW_cap`) für den
> Ausweichwert. Trefferwürfel gibt es nicht mehr: sobald eine Klassennotiz (`Prüfling.md`)
> `TP_pro_Stufe` / `RP_pro_Stufe` angibt, berechnet die App `hp.max` / `resilience.max` selbst.
