---
tags:
  - Regeln/Endeavour/WIP
---
# `=this.file.name`
Dein Held ist das Mittel, mit dem du deinen Abdruck in der Welt hinterlassen wirst. 
So erschaffst du deinen eigenen Helden:

## Schritt 1: Wähle deine Klasse
Dies hat den größten Einfluss auf deine weiteren Entscheidungen und darauf, wie dein Charakter mit der Welt interagiert:
```dataview
TABLE WITHOUT ID

file.link AS "Klasse",
Beschreibung

FROM #Regeln/Endeavour/Charakter/Klasse 

SORT file.name
```

## Schritt 2: Wähle deine Herkunft
Wähle eine [[Abstammungen|Abstammung]].
Wähle außerdem entweder aus den vorgefertigten [[Hintergründe|Hintergründen]] oder lege deine eigene Abenteuer-Motivation fest. 
Was hat deinen Helden angetrieben, ein Abenteurer zu werden? 
Wie kennst du die anderen Helden?

## Schritt 3: Fülle dein Charakterblatt aus
Benutze die [[Character Sheet Vorlage]].
Dieses Blatt hilft dir, Werte, Fähigkeiten, Ausrüstung und andere wichtige Informationen zu verwalten.

# Das Charakterblatt

## 1. Grundwerte & Attribute
Trage Charakterdetails ein: Name, [[Abstammungen|Abstammung]], [[Klassen|Klasse]], Stufe, Größe und Gewicht.
Markiere [[Vorteil und Nachteil|Vorteil]]  und [[Vorteil und Nachteil|Nachteil]] bei [[Rettungswürfe|Rettungswürfen]] und wähle eine Werteverteilung. 
(Tipp: Setze die höchsten Zahlen in die Kernattribute deiner Klasse).

- **Standard:** +2, +2, +1, +1, +0, +0, +0, -1
- **Ausgeglichen:** +2, +1, +1, +1, +1, +1, +0, -1
- **Extrem (Min–Max):** +3, +1, +1, +1, +1, +0, -1, -1

> [!example]- Beispiel  
> Der [[Berserker]] hat [[Stärke|ST]] und [[Instinkt|IN]] als Kernattribute. in dieser Prioritätsreihenfolge, und [[Entschlossenheit|EN]] als wichtigsten sekundären Wert. 
> Mit der Extrem-Verteilung (Min–Max) setzt du +3 auf [[Stärke|ST]], +1 auf [[Instinkt|IN]], +1 auf [[Beweglichkeit|BW]], +1 auf [[Konstitution|KO]], +1 auf [[Entschlossenheit|EN]], +0 auf [[Geschick|GE]], –1 auf [[Verstand|VS]] und –1 auf [[Präsenz|PR]]. 
> Markiere [[Vorteil und Nachteil|Vorteil]] für [[Stärkerettungswürfe|ST-Rettungswürfe]] und [[Konstitutionsrettungswürfe|KO-Rettungswürfe]], [[Vorteil und Nachteil|Nachteil]] für [[Verstandsrettungswürfe|VS-Rettungswürfe]] und [[Präsenzrettungswürfe|PR-Rettungswürfe]].

## 2. Fertigkeitspunkte
Auf Stufe 1 überträgst du deine [[Attribute|Attributsboni]] auf die jeweiligen [[Fertigkeiten]] (z. B. ein Held mit +2 [[Geschick|GE]] trägt +2 bei [[Fingerfertigkeit]] und [[Heimlichkeit]] ein) und darf **6 weitere Punkte frei verteilen**.

> [!example]- Beispiel  
> Wenn du –1 [[Verstand|VS]] hast, markiere -1 bei [[Magiekunde]], [[Geschichte]], [[Heilkunde]], [[Nachforschung]], [[Naturkunde]] und [[Religion]]. 
> Wiederhole das für deine anderen Attribute. 
> Mit den 6 Extrapunkten kannst du z. B. [[Heimlichkeit]] und [[Fingerfertigkeit]] je +3 erhöhen, 6 verschiedene Fertigkeiten  je +1 oder alle 6 Punkte in deine Lieblingsfertigkeit setzen.

## 3. Sekundäre Werte
Trage deine sekundären Werte ein:
- [[Initiative#Instinktwurf|Initiativebonus]] (Standard: [[Instinkt|IN]], bestimmt die Zugreihenfolge; [[Beweglichkeit|BW]] bestimmt separat die Start-AP in der ersten Runde, siehe [[Initiative]])
- [[Größenkategorie]]
- [[Bewegungsrate]] (abhängig von der [[Abstammungen|Abstammung]])
- maximale [[Erschöpfung]] (Standard: 6) 
- [[Gepäck]] (15 + [[Stärke|ST]] x 2 Plätze) und [[Schnellzugriff]] (bis zu 6 Behälter)

### [[Trefferpunkte]]  pro Stufe
Diese errechnen sich aus dem Basiswert der [[Klassen|Klasse]] plus eventueller Boni aus [[Abstammungen|Abstammung]], [[Subklassen|Subklasse]], [[Konstitution]], etc. 

### Maximale [[Trefferpunkte]] 
Auf Stufe 1 erhältst du maximale [[Trefferpunkte]] in Höhe der [[Trefferpunkte]] pro Stufe mal zwei.
 
### [[Resilienzpunkte]] pro Stufe
Diese errechnen sich aus dem Basiswert der [[Klassen|Klasse]] plus eventueller Boni aus [[Abstammungen|Abstammung]], [[Subklassen|Subklasse]], [[Entschlossenheit]] geteilt durch 2 (abgerundet), etc.

### Maximale [[Resilienzpunkte]] 
Auf Stufe 1 erhältst du maximale [[Resilienzpunkte]] in Höhe der [[Resilienzpunkte]] pro Stufe mal zwei.

## 4. Ausrüstung & Geld
Helden beginnen auf Stufe 1 mit der für ihre [[Klassen|Klasse]] und ihren [[Hintergründe|Hintergrund]] vorgeschriebenen Ausrüstung oder mit **50 GM**, um ihre Startausrüstung zu kaufen. 
Wenn du auf höherer Stufe beginnst, multipliziere den Betrag mit deiner Startstufe.

> [!faq]- Aber mein Charakter ist ein wohlhabender Adliger!  
> Kein Problem – dein Charakter hat momentan nur Zugang zu diesem Goldbetrag. 
> Warum sein Vermögen derzeit unerreichbar ist, liegt an dir und dem SL; es könnte ein guter Abenteueraufhänger sein, den vollen Reichtum freizuschalten.

## 5. Sprachen
Alle Helden sprechen [[Gemeinsprache]] (Standard). 
Jeder Punkt in [[Verstand|VS]] gewährt eine weitere bekannte [[Sprachen|Sprache]]. 

> [!tip]- GROFWINT DRAZLON!  
> Die Sprache einer anderen Kreatur zu sprechen kann Türen öffnen, die Waffen nicht können – wer bewaffnet ist, aber nicht kommunizieren kann, führt oft zum Kampf.

## 6. Weitere Fähigkeiten
Trage besondere Fähigkeiten ein, die du durch [[Klassen|Klasse]], [[Abstammungen|Abstammung]], [[Hintergründe|Hintergrund]] oder ähnliche Quellen erhältst.

## 7. Inventar
Jeder Held trägt ein [[Gepäck]] und bis zu 6 [[Schnellzugriff|Schnellzugriffsbehälter]].
[[Gepäck]] fasst 15 + [[Stärke|ST]] x 2 Plätze. Werden mehr Plätze belegt, ist der Charakter [[Belastet]].
Jeder [[Schnellzugriff|Schnellzugriffsbehälter]] fasst 1 Platz der [[Gegenstandsgrößen|Gegenstandsgröße]] Klein.
Wie viele Plätze ein Gegenstand braucht, bestimmt seine [[Gegenstandsgrößen|Gegenstandsgröße]].

> [!tip]- Über Munition  
> In den meisten Spielen musst du Munition nicht genau verfolgen. 
> Wenn du einen Köcher hast, hast du genug Pfeile. 
> Man geht davon aus, dass der Held Pfeile einsammelt, herstellt oder in einer Stadt nachkauft.