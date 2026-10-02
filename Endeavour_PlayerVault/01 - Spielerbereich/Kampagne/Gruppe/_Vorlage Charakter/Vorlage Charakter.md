---
# ═══════════════════════════════════════════════════════════════════════════════════════════════
#  VORLAGE CHARAKTERBOGEN — Anleitung: [[Anleitung Neuer Charakter]] (im selben Ordner)
#  Kopieren, umbenennen in `<Charaktername>.md`, dann überall CHARNAME durch den Dateinamen
#  ersetzen (Strg+H) und die Werte unten ausfüllen. Zeilen mit „# ←“ sind Pflicht.
# ═══════════════════════════════════════════════════════════════════════════════════════════════
type: character # ← nicht ändern: daran erkennt die Companion-App den Charakterbogen
name: CHARNAME # ← Anzeigename (darf vom Dateinamen abweichen, z. B. mit Beiname)
portrait: "[[CHARNAME Portrait.jpg]]" # Bild unter `_Attachments/` im Charakterordner; .jpg/.png/.webp/.svg
tags: [] # ← beim echten Charakter: [Charakter/GORN] — dann erscheint er in [[Gruppe]] (die Vorlage selbst bewusst nicht)

# ─── Klasse & Herkunft ──────────────────────────────────────────────────────────────────────────
class: # ← Name exakt wie die Klassennotiz unter `Charaktere/Klassen/` (Arkanist, Berserker, Fluchwirker, Gauner, Kleriker, Mönch, Naturalist, Paladin, Taktiker, Waldläufer)
  - name: Taktiker
    level: 1
    # subclass: … # optional; Multiclass = weiterer Listeneintrag, Startklasse zuerst
species: Mensch # ← Spezies/Volk
background: Soldat # ← Hintergrund (D&D-Sinn: Soldat, Gelehrte, …)
alignment: Neutral # ← Gesinnung
experience: 0 # Erfahrungspunkte
# formation: vorne # optional: vorne | mitte | hinten — überschreibt die Klasse in der Gruppenaufstellung

# ─── Attribute & Fertigkeiten (Regeln/Allgemein/Attribute bzw. Fertigkeiten) ───────────────────
nimble_attributes: # ← jedes Attribut −5 … +5
  st: 0 # Stärke
  bw: 0 # Beweglichkeit
  ko: 0 # Konstitution
  ge: 0 # Geschick
  in: 0 # Instinkt
  vs: 0 # Verstand
  pr: 0 # Präsenz
  en: 0 # Entschlossenheit
nimble_skills: # nur trainierte Fertigkeiten eintragen, je 0 … +10 (Schlüssel siehe Anleitung)
  perception: 1
# Interne Brücke für Zauber-SG/-Angriff (noch nicht auf Endeavour umgestellt):
# je 10 + 2 × Attributswert — st→str, bw→dex, ko→con, vs→int, in→wis, pr→cha
abilities: { str: 10, dex: 10, con: 10, int: 10, wis: 10, cha: 10 }
proficiency_bonus: 2
saving_throw_proficiencies: [] # bleibt leer — Vorteil/Nachteil kommt aus der Klassennotiz
skill_proficiencies: [] # bleibt leer — Training steht in nimble_skills

# ─── Ausrüstung (Werte stehen in den Notizen unter `Gegenstände/`) ─────────────────────────────
armor: # getragene Rüstung als Link, z. B. "[[Lederrüstung]]"; leer = keine. RK + Max BW rechnet die App daraus
armor_class: 0 # nur für Obsidian; die App nimmt die RK der verlinkten Rüstung
# shield: "[[Holzschild]]" # optional
attacks: # Waffen als Links, Schaden/Reichweite/Eigenschaften kommen aus der Waffennotiz
  - "[[Dolch]]"
speed: 30 ft # Bewegung; „30 ft“ = 6 Felder (der Obsidian-Bogen rechnet in ft, die App versteht auch „9 m“)

# ─── Lebenskraft (Max-Werte rechnet die App aus BasisTP/BasisRP der Klasse) ─────────────────────
hp:
  current: 4
  max: 4 # für Obsidian mitpflegen: (Stufe + 1) × (BasisTP + KO)
  temp: 0
resilience:
  current: 4
  max: 4 # für Obsidian mitpflegen: (Stufe + 1) × (BasisRP + EN/2 abgerundet)
conditions:
  exhaustion: 0 # 0 … 6
  # notes: Freitext zu aktuellen Verletzungen/Zuständen

# ─── Sinne, Sprachen, Merkmale ──────────────────────────────────────────────────────────────────
senses: {} # z. B. { darkvision: 18 m }
languages: [Gemeinsprache]
Merkmale: [] # Links auf #Merkmal-Notizen, z. B. - "[[Dunkelsicht]]" (Einsatz-Feld steuert Aktion/Reaktion/Passiv)

# ─── Biografie (alles optional, füllt den App-Tab „Biografie“) ─────────────────────────────────
backstory: |
  Vorgeschichte in ein paar Absätzen. Leerzeile = neuer Absatz; [[Wikilinks]] sind erlaubt.
Persönlichkeit:
  Persönlichkeitsmerkmale:
    - Erstes Merkmal
    - Zweites Merkmal
  Ideale: Woran glaubt der Charakter?
  Bindungen: Wem oder was fühlt er sich verpflichtet?
  Makel: Seine Schwäche
Aussehen: # einzelne Felder weglassen oder ganz als Freitext schreiben: `Aussehen: Groß, rote Haare, …`
  Geschlecht:
  Alter:
  Größenkategorie: Mittel
  Größe:
  Gewicht:
  Augenfarbe:
  Haarfarbe:
  Hautfarbe:
---

![[CHARNAME Portrait.jpg|160]]

# `=this.name`

***`$= dv.fileLink(dv.current().class[0].name)` `=this.class[0].level`** · `=this.species` · `=this.background` · `=this.alignment` · `=this.experience` EP*

> [!tip] Charakterbogen nach dem Aufbau des Nimble-Bogens
> Alle Zahlen kommen live aus den Metadaten dieser Notiz, aus [[Spell Sheet CHARNAME]] und [[Inventar CHARNAME]]. Felder mit
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
const mod = (n) => `${n - 2 * exh >= 0 ? "+" : ""}${n - 2 * exh}`;
const roll = (n) => `\`dice: 1d20${mod(n)}\``;
// Kernattribute und Klassen-Rettungswürfe (Vorteil/Nachteil) kommen aus der Klassennotiz.
const klasse = dv.page(c.class[0].name);
const linked = (list) => (list ?? []).map((l) => (l?.path ?? String(l)).split("/").pop().replace(/\.md$/, ""));
const core = linked(klasse?.Kernattribute);
const adv = linked(klasse?.Rettungswürfe?.Vorteil);
const dis = linked(klasse?.Rettungswürfe?.Nachteil);
const saveNotes = {
  st: "Stärkerettungswürfe", bw: "Beweglichkeitsrettungswürfe", ko: "Konstitutionsrettungswürfe",
  vs: "Verstandsrettungswürfe", pr: "Präsenzrettungswürfe", en: "Entschlossenheitsrettungswürfe",
};
const saveRoll = (k) => {
  const note = saveNotes[k];
  if (adv.includes(note)) return `\`dice: 2d20kh1${mod(a[k])}\` **Vorteil**`;
  if (dis.includes(note)) return `\`dice: 2d20kl1${mod(a[k])}\` *Nachteil*`;
  return roll(a[k]);
};
const attrs = [
  ["st", "Stärke", true], ["bw", "Beweglichkeit", true], ["ko", "Konstitution", true], ["ge", "Geschick", false],
  ["in", "Instinkt", false], ["vs", "Verstand", true], ["pr", "Präsenz", true], ["en", "Entschlossenheit", true],
];
dv.table(
  ["Attribut", "Wert", "Probe", "Rettungswurf"],
  attrs.map(([k, name, save]) => [
    core.includes(name) ? `**[[${name}]]** ⭐` : `[[${name}]]`,
    `**${fmt(a[k])}**`,
    roll(a[k]),
    save ? saveRoll(k) : "—",
  ])
);
```

*⭐ = Kernattribut der Klasse. Vorteil/Nachteil auf Rettungswürfe gibt die Klassennotiz vor. Ge und In haben keinen eigenen Rettungswurf, sie treiben Angriffe bzw. Initiative ([[Rettungswürfe]]).*

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
// Die Waffenwerte kommen aus den Waffennotizen (Gegenstände/Waffen/Waffen), der Bonus aus den
// Attributen: Nahkampf und Wurf mit ST, Fernkampf mit GE, Finesse wahlweise ST oder GE (der höhere).
const c = dv.current();
const a = c.nimble_attributes;
const exh = c.conditions?.exhaustion ?? 0;
const fmt = (n) => (n >= 0 ? "+" : "−") + Math.abs(n);
const plain = (n) => (n >= 0 ? "+" : "") + n;
const atk = (n) => `\`dice: 1d20${plain(n - 2 * exh)}\``;
const name = (l) => (l?.path ?? String(l)).split("/").pop().replace(/\.md$/, "");
const meters = (...parts) => {
  const v = parts.filter((p) => p !== null && p !== undefined && p !== "").map((p) => String(p).replace(/\s*\(\d+\)$/, ""));
  return v.length ? `${v.join("/")} m` : "—";
};
const rows = [];
for (const entry of c.attacks ?? []) {
  const w = entry?.path ? dv.page(entry.path) : null;
  if (!w) continue;
  const props = (w.Eigenschaften ?? []).map(name);
  const propsFern = (w.EigenschaftenFern ?? []).map(name);
  const finesse = [...props, ...propsFern].includes("Finesse");
  const thrown = (w.file.tags ?? []).some((t) => t.includes("Wurfwaffe")) || propsFern.includes("Wurfwaffe");
  const pick = (ranged) => (ranged ? ["GE", a.ge] : finesse && a.ge > a.st ? ["GE", a.ge] : ["ST", a.st]);
  const row = (label, dice, type, range, list, ranged) => {
    if (!dice) return;
    const [attr, bonus] = pick(ranged);
    rows.push([
      label,
      `${fmt(bonus)} ${atk(bonus)} <small>${attr}</small>`,
      `\`dice: ${dice}${bonus ? plain(bonus) : ""}\` ${type ?? ""}`,
      range,
      list.map((p) => `[[${p}]]`).join(", "),
    ]);
  };
  row(w.file.link, w.Schaden, w.Schadensart, meters(w.Reichweite), props, false);
  const fernLabel = w.Schaden ? `${w.file.link} (${thrown ? "Wurf" : "Fernkampf"})` : w.file.link;
  row(fernLabel, w.SchadenFern, w.SchadensartFern, meters(w.Range1, w.Range2, w.Range3), propsFern, !thrown);
}
dv.table(["Waffe", "Angriff", "Schaden", "Reichweite", "Eigenschaften"], rows);
```

*Angriffswurf gegen den [[Ausweichwert]] des Ziels, die [[Rüstungsklasse]] verringert danach den Schaden ([[Angriff]]).*

## ✨ Magie

*Nur für Zauberwirker — bei Klassen ohne Magie diesen Abschnitt bis „🧙 Klasse“ löschen und keine [[Spell Sheet CHARNAME]] anlegen.*

| 🔮 [[Mana]] | Höchster Grad | Zauberattribut (KEY) | Zauber-SG | Zauberangriff |
|:---:|:---:|:---:|:---:|:---:|
| `INPUT[number:Spell Sheet CHARNAME#spellcasting.mana.current]` / `VIEW[{Spell Sheet CHARNAME#spellcasting.mana.max}]` | `VIEW[{Spell Sheet CHARNAME#spellcasting.max_tier}]` | `$= "VS " + (dv.current().nimble_attributes.vs >= 0 ? "+" : "") + dv.current().nimble_attributes.vs` | `$= 8 + dv.current().proficiency_bonus + Math.floor((dv.current().abilities.int - 10) / 2) - 2 * (dv.current().conditions?.exhaustion ?? 0)` | `$= "+" + (dv.current().proficiency_bonus + Math.floor((dv.current().abilities.int - 10) / 2))` |

*Ein Zauber kostet so viel Mana wie sein Grad, Zaubertricks und Hilfszauber sind kostenlos. Hochstufen bis zum höchsten freigeschalteten Grad kostet den gewählten Grad. Feldrast: halbes Mana zurück, Sichere Rast: alles.*

```dataviewjs
const c = dv.current();
const sheet = dv.page(c.file.folder + "/Spell Sheet CHARNAME");
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

## 🧙 Klasse

```dataviewjs
const c = dv.current();
const a = c.nimble_attributes;
const klasse = dv.page(c.class[0].name);
const lvl = c.class[0].level;
const names = (list) => (list ?? []).filter(Boolean).map((l) => (l?.path ? dv.fileLink(l.path, false, l.display) : String(l))).join(", ") || "—";
if (!klasse) {
  dv.paragraph(`> [!warning] Keine Klassennotiz „${c.class[0].name}“ gefunden.`);
} else {
  const ko = a.ko, en = Math.floor(a.en / 2);
  const tp = (lvl + 1) * (klasse.BasisTP + ko);
  const rp = (lvl + 1) * (klasse.BasisRP + en);
  dv.table(
    ["Klasse", "Kernattribute", "Waffen", "Rüstung", "Max. TP", "Max. RP"],
    [[
      `${klasse.file.link} ${lvl}`,
      names(klasse.Kernattribute),
      names(klasse.Übung?.Waffen),
      names(klasse.Übung?.Rüstungen),
      `**${tp}**<br><small>(${lvl} + 1) × (${klasse.BasisTP} + KO ${ko})</small>`,
      `**${rp}**<br><small>(${lvl} + 1) × (${klasse.BasisRP} + EN/2 ${en})</small>`,
    ]]
  );
}
```

*Stufe 1 zählt doppelt: (BasisTP + KO) × 2, danach je Stufe BasisTP + KO; RP genauso mit BasisRP und EN/2 abgerundet (siehe Klassennotiz).*

## 🏕️ Rasten

| Rast | Dauer | Erholung |
|---|---|---|
| [[Verschnaufen]] | 10 Min., bis 2×/Tag | 50 % der max. RP |
| [[Feldrast]] | 8 Std. im Lager, 1×/Tag | alle RP, 25 % der max. TP, halbes Mana |
| [[Sichere Rast]] | 8 Std. am sicheren Ort, 1×/Tag | alle RP, 50 % der max. TP, alles Mana, −1 Erschöpfung, temp. TP enden |

## 🎒 Ausrüstung & Sinne

- **Rüstung:** `=choice(this.armor, this.armor, "keine")` (RK `=this.armor_class`)
- **Waffen:** `=this.attacks`
- **Inventar:** [[Inventar CHARNAME]]
- **Zauber:** [[Spell Sheet CHARNAME]]
- **Sinne:** `=choice(this.senses.darkvision, "Dunkelsicht " + this.senses.darkvision, "—")`
- **Sprachen:** `=this.languages`
- **Merkmale:** `=this.Merkmale`

## 📜 Hintergrund

```dataviewjs
dv.paragraph("> [!quote] " + dv.current().species + "\n> " + String(dv.current().backstory).trim().replace(/\n/g, "\n> "));
```

## 🎭 Persönlichkeit & Aussehen

```dataviewjs
const c = dv.current();
const p = c.Persönlichkeit ?? {};
const traits = (p.Persönlichkeitsmerkmale ?? []).filter(Boolean);
if (traits.length) dv.paragraph("**Persönlichkeitsmerkmale**\n" + traits.map((t) => "- " + t).join("\n"));
for (const key of ["Ideale", "Bindungen", "Makel"]) {
  if (p[key]) dv.paragraph(`**${key}:** ${p[key]}`);
}
const look = Object.entries(c.Aussehen ?? {}).filter(([, v]) => v !== null && v !== "");
if (look.length) dv.table(["Aussehen", ""], look);
```

---

> [!note]- Vorlage — zum Aufklappen
> Erstellt aus der Vorlage unter `Kampagne/Gruppe/_Vorlage Charakter/`. Was wohin gehört, steht in
> [[Anleitung Neuer Charakter]]. Der Bogen speichert keine eigenen Zahlen: alles oben wird per Dataview aus
> den Metadaten gelesen und per Meta-Bind in dieselben Felder geschrieben, die auch die Companion-App liest
> und schreibt. Benötigt die Plugins Dataview (mit JavaScript), Meta Bind und Dice Roller.
