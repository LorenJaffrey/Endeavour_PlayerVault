---
# VORLAGE SPELL SHEET — nur für Zauberwirker. Umbenennen in `Spell Sheet <Charaktername>.md`, CHARNAME ersetzen.
Charakter: "[[CHARNAME]]" # ← Link auf die Charakterdatei (Dateiname!), so findet die App die Zauber
spellcasting:
  ability: int # Brücke für Zauber-SG/-Angriff (int = Verstand); siehe `abilities` im Charakterbogen
  mana:
    current: 3
    max: 3 # Mana-Maximum = (Zauberattribut × 3) + Stufe — Formel ggf. aus der Klassennotiz
  max_tier: 0 # höchster freigeschalteter Zaubergrad (0 = nur Zaubertricks)
spells_known: # Links auf Zaubernotizen (`type: spell`, Vorlage siehe [[Anleitung Neuer Charakter]])
  - "[[Zaubername]]"
---

Zauber zu [[CHARNAME]]. Ein Zauber kostet so viel [[Mana]] wie sein Grad, Zaubertricks und Hilfszauber sind
kostenlos. Hochstufen bis zum höchsten freigeschalteten Grad (`max_tier`), Kosten = gewählter Grad.
