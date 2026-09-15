---
tags:
  - Regeln/Nimble/Schaden
aliases:
  - Schadensmodifikator
---
# `=this.file.name`
Manche Kreaturen, Gegenstände, Effekte oder Zustände verändern, wie stark sie von bestimmten [[Schadensarten]] betroffen sind. 
Diese Veränderungen werden als [[Schadensmodifikatoren]] bezeichnet. 
[[Schadensmodifikatoren]] beziehen sich immer auf eine bestimmte [[Schadensarten|Schadensart]] oder auf eine klar benannte Schadensquelle.
Ein Typmodifikator kann sich statt auf eine einzelne Schadensart auch auf eine ganze [[Schadenskategorien|Schadenskategorie]] beziehen. 
"Schadensresistenz: [[Physischer Schaden]]" deckt dann automatisch [[Hiebschaden]], [[Stichschaden]] und [[Wuchtschaden]] gleichzeitig ab, statt jede einzeln aufzuführen.

Es gibt zwei Arten von [[Schadensmodifikatoren]]: **flache Modifikatoren** und **Typmodifikatoren**. 
Flache Modifikatoren verändern den Schaden um einen festen Wert, etwa +5 oder -10. 
Typmodifikatoren legen fest, ob eine Kreatur gegen eine [[Schadensart]] immun, resistent oder anfällig ist.

## Flache Modifikatoren
Flache Modifikatoren erhöhen oder verringern den verursachten Schaden um einen festen Wert. 
Ein Bonus von +5 erhöht den Schaden um 5, ein Malus von -10 verringert den Schaden um 10. 
Sinkt der Schaden dadurch unter 0, wird er stattdessen auf 0 gesetzt.
Die [[Rüstungsklasse]] ist das typische Beispiel für einen flachen Modifikator: sie reduziert eingehenden Schaden um einen festen Wert.

## Typmodifikatoren
**[[Schadensimmunität]]** bedeutet, dass eine Kreatur von einer bestimmten [[Schadensarten|Schadensart]] keinen Schaden erleidet.  
**[[Schadensresistenz]]** bedeutet, dass eine Kreatur gegen eine bestimmte [[Schadensarten|Schadensart]] nur den halben Schaden erleidet.  
**[[Schadensanfälligkeit]]** bedeutet, dass eine Kreatur gegen eine bestimmte [[Schadensarten|Schadensart]] doppelten Schaden erleidet.

Mehrere gleiche Typmodifikatoren auf dieselbe [[Schadensart]] werden nicht addiert. 
Eine Kreatur mit mehrfacher [[Schadensresistenz]] gegen dieselbe [[Schadensart]] bleibt einfach resistent, und eine Kreatur mit mehrfacher [[Schadensanfälligkeit]] bleibt einfach anfällig.
Treffen [[Schadensresistenz]] und [[Schadensanfälligkeit]] gleichzeitig auf dieselbe [[Schadensart]] zu, heben sie sich gegenseitig auf.

## Reihenfolge der Anwendung
Wenn Schaden durch [[Schadensmodifikatoren]] verändert wird, wird er in folgender Reihenfolge abgehandelt:

1. Zuerst wird geprüft, ob eine **[[Schadensimmunität]]** vorliegt. Ist das der Fall, wird der Schaden auf 0 gesetzt und keine weiteren Berechnungen angestellt. Das gilt auch bei einem [[Kritische Treffer|Kritischen Treffer]], siehe [[Kritische Treffer]].
2. Danach werden alle **flachen Modifikatoren** auf den Schaden angewendet (z.B. [[Rüstungsklasse]]).
3. Anschließend wird eine vorhandene **[[Schadensresistenz]]** angewendet.
4. Zuletzt wird eine vorhandene **[[Schadensanfälligkeit]]** angewendet.

Ergibt eine Halbierung einen ungeraden Wert, wird der Schaden abgerundet.

>[!Example] Beispiel
>Eine Kreatur hat [[Rüstungsklasse]] 5, ist [[Schadensresistenz|resistent]] gegen [[Feuerschaden]] und [[Schadensanfälligkeit|anfällig]] für [[Kälteschaden]].
>Erleidet sie 28 [[Feuerschaden]]: keine Immunität, die [[Rüstungsklasse]] reduziert den Schaden auf 23, die Resistenz gegen [[Feuerschaden]] halbiert ihn auf 11 (abgerundet), die Anfälligkeit betrifft nur [[Kälteschaden]] und ändert hier nichts. Sie erleidet 11 Schaden.
>Würde sie stattdessen 28 [[Kälteschaden]] erleiden, würde die [[Rüstungsklasse]] ihn ebenso auf 23 reduzieren, aber ihre Anfälligkeit gegen [[Kälteschaden]] ihn anschließend auf 46 verdoppeln (keine Resistenz gegen Kälte).