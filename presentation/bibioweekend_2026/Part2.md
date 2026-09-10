---
marp: true
theme: default
paginate: true
header: "Scratch Jump'n'Run Workshop"
footer: "Teil 2: Schwerkraft und Levelbau"
style: |
  section {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
  h1 { color: #e91e63; }
  h2 { color: #555; }
  code { background: #f0f0f0; color: #2d5af0; }
---

# Teil 2: Physik und Level-Design 🛠️

**Heute bauen wir:**
1. Echte Schwerkraft (Gravity)
2. Springen wie Super Mario
3. Einen Level aus Klonen bauen

---

# Schritt 1: Die Schwerkraft (Gravity)

Damit unsere Figur nicht fliegt, brauchen wir eine Variable.

1. Erstelle eine Variable: `y-geschwindigkeit` (nur für diese Figur).
2. **Im "Wiederhole fortlaufend"-Block:**
   - `ändere y um (y-geschwindigkeit)`
   - `ändere y-geschwindigkeit um -2` (zieht die Figur nach unten)



---

# Schritt 2: Der Boden (Klon-Technik)

Anstatt 100 Sprites zu zeichnen, lassen wir Scratch die Arbeit machen!

1. Wähle das **Boden-Sprite** (von deinem Lehrer vorbereitet).
2. Erstelle eine Variable: `original_x` (**Nur für dieses Sprite!**).
3. **Skript für das Boden-Sprite:**
   - `Wiederhole 10 mal:`
     - `erzeuge Klon von mir selbst`
     - `ändere original_x um 50` (oder die Breite deines Sprites)

---

# Schritt 3: Den Boden platzieren

Damit die Klone an der richtigen Stelle erscheinen:

- **Wenn ich als Klon entstehe:**
  - `gehe zu x: (original_x) y: (-150)`
  - `zeige dich`

**Tipp:** Jetzt haben wir eine lange Plattform aus nur einem Sprite gebaut! 🎉

---

# Schritt 4: Landen auf dem Boden

Die Figur soll nicht durch den Boden fallen! Wir nutzen unseren Spezial-Block.

1. Erstelle einen **eigenen Block**: `Landen` (Klicke auf "Ohne Bildschirmaktualisierung laufen lassen"!).
2. **Inhalt von `Landen`:**
   - `Falls <wird Boden berührt?> dann:`
     - `Wiederhole bis <wird Boden NICHT berührt?>:`
       - `ändere y um 1`
     - `setze y-geschwindigkeit auf 0`



---

# Schritt 5: Springen! 🚀

Jetzt, wo wir fest auf dem Boden stehen, können wir springen.

- **Im Haupt-Skript der Figur:**
  - `Falls <Taste Pfeil nach oben gedrückt?> UND <wird Boden berührt?> dann:`
    - `setze y-geschwindigkeit auf 15`

**Wichtig:** Man kann nur springen, wenn man den Boden berührt! (Kein Fliegen!)

---

# Schritt 6: Musik und Stimmung 🎵

Ein Spiel ohne Sound ist nur ein halbes Spiel.

1. Wähle den Block `spiele Klang [bgm] ganz oder bis zu Ende`.
2. Platziere ihn in einem eigenen `Wenn Flagge angeklickt wird` -> `Wiederhole fortlaufend` Skript.

---

# Zusammenfassung & Spielen! 🎉

**Was wir gelernt haben:**
- **Variablen:** Für Geschwindigkeit und Position.
- **Klone:** Um schnell große Level zu bauen.
- **Eigene Blöcke:** Um Fehler (Ruckeln) zu vermeiden.

**Jetzt bist du dran:** Verändere die Schwerkraft oder die Sprunghöhe. Wie fühlt sich das Spiel an?
