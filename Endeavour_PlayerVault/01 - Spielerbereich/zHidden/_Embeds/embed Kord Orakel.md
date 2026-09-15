<div id="kord-oracle" style="
  margin: 1em 0;
  padding: 1em;
  border: 2px solid #1a73e8;
  border-radius: 10px;
  text-align: center;
  background: #111828;
  color: #b0c4de;
  font-family: 'Inter', sans-serif;
  max-width: 100%;
  box-shadow: 0 0 8px rgba(30, 144, 255, 0.5);
">
  <h3 style="color:#4aa3ff; margin-bottom:0.5em;">Orakel von Kord</h3>
  <div id="oracle-output" style="margin-top:1em; font-size:1.1em; min-height:2em;"></div>
  <br />
  <button id="oracle-btn" style="
    padding: 0.5em 1em;
    border: none;
    border-radius: 6px;
    background: #0d4f8b;
    color: #ffffff;
    font-size: 1em;
    cursor: pointer;
    box-shadow: 0 0 6px #0d4f8b;
    transition: background 0.2s, box-shadow 0.2s;
  " onmouseover="this.style.background='#1e90ff'; this.style.boxShadow='0 0 10px #1e90ff';"
     onmouseout="this.style.background='#0d4f8b'; this.style.boxShadow='0 0 6px #0d4f8b';">
    Befrage Kord
  </button>
</div>

```js-engine
const answers = [
  // Mut / Angriff
  "Kord ruft: Greife ohne Zögern an!",
  "Ein Blitz befiehlt: Stürze dich in die Schlacht!",
  "Donner hallt: Dein Mut ist dein Schild.",
  "Kords Lachen donnert: Kämpfe wie der Sturm selbst!",
  "Der Sturm treibt dich: Führe den ersten Schlag!",
  "Kord brüllt: Lass keine Furcht in deinem Herzen!",
  "Die Wolken brechen: Dein Schwert soll leuchten.",
  "Ein Blitzschlag: Töte den Zweifel, bevor er dich tötet.",
  "Der Donner zwingt dich: Handle jetzt!",
  "Kords Stimme: Dein Mut ist größer als ihre Zahl.",

  // Vorsicht / Warten
  "Der Sturm spricht: Warte den richtigen Moment ab.",
  "Ein fernes Grollen: Die Zeit ist noch nicht reif.",
  "Kords Schweigen: Geduld ist deine Waffe.",
  "Blitze flackern: Zögere – der Sturm hält den Atem an.",
  "Der Wind mahnt: Ruhe vor dem Sturm bringt Sieg.",
  "Ein Donnerschlag: Pausiere, ehe du den Schritt wagst.",
  "Der Regen flüstert: Warte, bis der Boden gefestigt ist.",
  "Ein Sturmauge erscheint: In der Ruhe liegt Klarheit.",
  "Kords Warnung: Ein falscher Schritt kostet alles.",
  "Der Himmel schweigt: Geduld prüft deine Stärke.",

  // Prüfung / Herausforderung
  "Kords Ruf: Stärke entsteht, wenn du das Unmögliche wagst.",
  "Donner rollt: Dein Weg ist eine Prüfung.",
  "Ein Blitz zeigt: Nur durch Schmerz wächst Macht.",
  "Kord zürnt: Du wirst geprüft, sei bereit.",
  "Der Sturm jagt: Folge dem Pfad der größten Gefahr.",
  "Ein heulender Wind: Dein Herz ist dein Richter.",
  "Kords Zorn: Zerstöre, was dich fesselt.",
  "Ein Wetterleuchten: Deine Prüfung steht bevor.",
  "Der Sturmkreis: Dein Ende ist ein Anfang.",
  "Ein Blitzschlag: Deine Grenzen sind zu durchbrechen.",

  // Schicksal / Rätselhaft
  "Der Sturm schweigt – die Entscheidung liegt bei dir.",
  "Ein fernes Leuchten: Folge dem unerwarteten Weg.",
  "Kord flüstert: Dein Mut ist dein Kompass.",
  "Die Wolken formen Zeichen: Lies, was verborgen ist.",
  "Der Donner spricht in Rätseln: Was du suchst, sucht dich.",
  "Ein Regenbogen: Hoffnung verbirgt Gefahr.",
  "Kords Schatten: Was du fürchtest, wird dich führen.",
  "Der Wind trägt Stimmen: Höre auf das Unhörbare.",
  "Ein Blitz zerreißt die Dunkelheit: Die Wahrheit liegt offen.",
  "Ein Grollen mahnt: Das Schicksal lässt sich nicht lenken.",

  // Göttliche Stimme
  "Kords Stimme donnert: Opfer bringen, bevor du forderst!",
  "Ein Sturmgesang: Dein Weg ist sein Geschenk.",
  "Kord befiehlt: Zerbrich die Ketten deiner Angst.",
  "Ein Donnerhall: Nur Tapfere verdienen Gehör.",
  "Kords Funken: Wage es, und du wirst wachsen.",
  "Der Wind ruft: Freiheit ist dein Gebet.",
  "Ein Strahl am Himmel: Hoffnung ist deine Waffe.",
  "Kords Augen funkeln: Stelle dich der Herausforderung.",
  "Donner verkündet: Es gibt keinen leichten Weg.",
  "Kord ruft: Die größte Prüfung liegt direkt vor dir.",

  // --- ab hier weitere Variationen, bis wir auf 150 kommen ---
  "Ein Sturmorkan: Dein Wille allein wird dich tragen.",
  "Kord ruft: Folge deinem Herzen, auch im Chaos.",
  "Der Blitz mahnt: Handle gerecht, auch im Sturm.",
  "Ein Sturmwind jagt: Laufe schneller als deine Zweifel.",
  "Kords Ruf: Wage, wo andere fliehen.",
  "Der Donner grollt: Deine Feinde sind deine Lehrer.",
  "Kord lacht: Dein Schmerz wird dich erheben.",
  "Ein Blitzschlag: Vernichte, was schwach ist.",
  "Der Wind bebt: Deine Wahl ist unausweichlich.",
  "Kords Sturm: Sieg durch Mut, niemals durch Angst.",
  "Ein Donnergrollen: Deine Stunde naht.",
  "Die Wolken toben: Dein Blut wird geprüft.",
  "Kord befiehlt: Sei stärker als dein Schatten.",
  "Ein grollendes Echo: Folge dem Ruf der Gefahr.",
  "Der Regen fällt: Reinige deine Seele.",
  "Kords Donner: Wähle Stärke über Bequemlichkeit.",
  "Ein Blitz erhellt: Der Weg liegt offen.",
  "Der Sturm peitscht: Deine Entschlossenheit wird geprüft.",
  "Kord spricht: Jede Wahl ist ein Kampf.",
  "Ein Sturmwind trägt: Deine Worte sind Waffen.",
  "Der Donner bebt: Deine Wahrheit wird offenbar.",
  "Ein Sturmauge mahnt: Hüte dich vor Übermut.",
  "Kords Ruf: Finde Freude im Kampf.",
  "Ein Blitzschlag: Breche den Kreis des Zweifels.",
  "Donner rollt: Folge nicht dem einfachsten Pfad.",
  "Ein Sturmkreis erscheint: Alles wiederholt sich.",
  "Der Regen rauscht: Dein Weg ist nicht allein.",
  "Kords Stimme: Fordere das Schicksal heraus.",
  "Ein Donnerfluch: Wage mehr, als du tragen kannst.",
  "Der Blitz brennt: Reinige, was verdorben ist.",
  "Kords Ruf: Wähle Mut vor Vorsicht.",
  "Ein Sturmgebrüll: Deine Kraft wird gebraucht.",
  "Donner bricht: Zögere nicht länger.",
  "Kords Donner: Nur durch Sturm wächst Größe.",
  "Der Wind kreischt: Deine Angst ist dein Feind.",
  "Ein Wetterleuchten: Etwas verbirgt sich im Dunkeln.",
  "Kord spricht: Wage die Prüfung ohne Furcht.",
  "Donner mahnt: Stärke bedeutet Verantwortung.",
  "Ein Blitz schneidet: Deine Entscheidung ist jetzt.",
  "Der Sturm grollt: Sei die Waffe, die du suchst.",
  "Kords Ruf: Lerne vom Donner – laut, klar, unaufhaltbar.",
  "Ein Blitzstrahl: Dein Mut ist Funke und Flamme.",
  "Der Regen mahnt: Geduld bewahrt dein Leben.",
  "Kord lacht: Nur durch Kampf wirst du frei.",
  "Ein Sturm bricht: Das Chaos ist deine Prüfung.",
  "Donner ruft: Handle mit Herz und Faust.",
  "Kords Sturm: Jede Schlacht ist ein Gebet.",
  "Der Blitz mahnt: Vergiss nicht, wer du bist.",
  "Ein Sturmwind: Deine Stärke liegt in Gemeinschaft.",
  "Donner lacht: Das Risiko ist dein Preis.",
  "Kords Stimme: Sei wie der Sturm – unberechenbar.",
  "Ein Blitzstrahl: Hoffnung ist deine schärfste Waffe.",
  "Der Regen weint: Verluste sind Teil des Weges.",
  "Kords Ruf: Stelle dich dem Sturm oder bleib im Schatten.",
  "Ein Donnerhall: Dein Ruf eilt dir voraus.",
  "Der Wind trägt: Freundschaft ist Stärke.",
  "Ein Blitz brennt: Zerstöre, was dich lähmt.",
  "Kords Lachen: Furcht ist ein Geschenk, nutze es.",
  "Ein Sturm heult: Dein Zorn ist dein Antrieb.",
  "Donner rollt: Jede Entscheidung ist endgültig.",
  "Kords Sturm: Nur im Chaos findest du Klarheit.",
  "Ein Blitz mahnt: Folge der schwereren Wahl.",
  "Der Wind rauscht: Dein Weg ist stürmisch, aber richtig.",
  "Kord spricht: Dein Mut heilt mehr als dein Zauber.",
  "Ein Donnerschlag: Aufstehen ist immer die Antwort.",
  "Der Sturm heult: Dein Wille erschafft Realität.",
  "Kords Stimme: Wähle mit Stärke, nicht mit Angst.",
  "Ein Blitz erhellt: Dein Herz kennt die Richtung.",
  "Donner mahnt: Nimm die Prüfung an, nicht den Ausweg.",
  "Ein Sturmwind: Handle, als würdest du beobachtet.",
  "Kord ruft: Sei Sturmbringer, nicht Staub im Wind.",
  "Der Regen mahnt: Wasche Zweifel aus deinem Geist.",
  "Ein Blitz bricht: Dein Entschluss muss fallen.",
  "Kords Ruf: Nichts ist größer als dein Mut.",
  "Donner hallt: Dein Weg wird belohnt.",
  "Ein Sturmkreis: Du bist der Anfang des Endes.",
  "Kord lacht: Wage es, die Götter zu fordern.",
  "Der Blitz zuckt: Folge deinem Instinkt.",
  "Ein Sturm schreit: Nur Mut öffnet Türen.",
  "Donner hallt: Deine Tat wird Legende.",
  "Kords Donner: Du bist der Funke, der Feuer entfacht.",
  "Ein Blitzschlag: Opfer bringen führt zu Sieg.",
  "Der Wind heult: Folge der Stimme in dir.",
  "Kord ruft: Sei furchtlos, sei frei.",
  "Donner grollt: Dein Zögern ist dein größter Feind.",
  "Ein Sturmwind mahnt: Stärke wächst im Widerstand.",
  "Kords Stimme: Sei wie der Blitz – schnell und rein.",
  "Ein Blitz bricht: Zerstöre, um Neues zu schaffen.",
  "Der Donner ruft: Wähle und geh voran.",
  "Ein Sturmkreis erscheint: Alles, was war, wird wieder sein.",
  "Kord spricht: Dein Mut ist dein Gebet.",
  "Donner lacht: Das Schicksal liebt die Kühnen.",
  "Ein Blitzstrahl: Folge dem Ruf der Freiheit.",
  "Kords Stimme: Wage es, das Unmögliche zu träumen.",
  "Ein Sturmwind jagt: Lauf deiner Bestimmung entgegen.",
  "Der Regen spricht: Reinheit ist deine Waffe.",
  "Ein Blitzschlag: Brich den Willen deiner Gegner.",
  "Kord ruft: Sei wie der Donner – unaufhaltsam.",
  "Ein Sturm grollt: Alles prüft dich, alles formt dich.",
  "Donner hallt: Dein Geist ist stärker als dein Körper.",
  "Kords Ruf: Sei die Flamme im Sturm.",
  "Ein Blitz brennt: Wahrheit zerstört die Lüge.",
  "Der Wind trägt: Deine Zukunft ist ungeboren.",
  "Ein Sturmwind mahnt: Folge dem Pfad des Schmerzes.",
  "Kord spricht: Jeder Sturm ist ein Lehrer.",
  "Donner mahnt: Dein Schicksal ist eine Prüfung.",
  "Ein Blitzstrahl: Zerschmettere, was dich hindert.",
  "Kords Donner: Du bist der Sturm, den du suchst."
  ];

  const btn = document.getElementById("oracle-btn");
  const output = document.getElementById("oracle-output");

  btn.addEventListener("click", () => {
    const choice = answers[Math.floor(Math.random()*answers.length)];
    output.textContent = choice;
    lightningAnimation();
  });

```