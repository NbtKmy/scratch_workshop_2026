---
marp: true
theme: default
paginate: true
header: "Scratch Jump'n'Run Workshop"
footer: "Teil 1: Grundlagen der Bewegung"
style: |
  section {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
  h1 { color: #2d5af0; }
  h2 { color: #555; }
  code { background: #f0f0f0; color: #e91e63; }
---

# Erstelle dein eigenes Jump'n'Run Spiel! 🐱🚀

**Teil 1: Die Figur zum Leben erwecken**

Workshop-Leiter: Nobu

---

# Was wir heute bauen werden

1. Eine Figur auswählen
2. Nach links und rechts laufen
3. Lauf-Animationen erstellen
4. Die Blickrichtung anpassen

**Lerne die Grundlagen der Spieleentwicklung!**

---

# Schritt 1: Wähle eine Spielfigur (Sprite)

1. Klicke unten rechts auf das **Katzen-Icon**.
2. Wähle eine Figur aus, die mehrere Kostüme hat.
   - **Empfehlung:** `Pico Walking`, `Giga Walking` oder `Avery Walking`.
   - **Warum?** Diese Figuren haben schon fertige Bilder für eine Geh-Animation.

---

# Schritt 2: Nach rechts laufen

Wir nutzen den "Falls ... dann"-Block, um auf Tasten zu reagieren.

- Kategorie `Steuerung`: Ziehe `Wiederhole fortlaufend` in das Skript.
- Ziehe einen `Falls ... dann`-Block hinein.
- Kategorie `Fühlen`: Setze `<Taste Pfeil nach rechts gedrückt?>` ein.
- **Aktion:** Kategorie `Bewegung` -> `ändere x um 10`.



---

# Schritt 3: Nach links laufen

Wenn Rechts "+10" ist, was ist dann Links? 🤔

- Kopiere den "Falls"-Block (Rechtsklick -> Duplizieren).
- Ändere die Taste auf `Pfeil nach links`.
- **Aktion:** `ändere x um -10`.

**Wichtig:** Ein Minus-Zeichen `-` bewegt die Figur nach links!

---

# Schritt 4: Die Lauf-Animation

Bisher rutscht die Figur nur über den Boden. Lass uns die Beine bewegen!

- Kategorie `Aussehen`: Ziehe `nächstes Kostüm` in beide "Falls"-Blöcke.
- Jetzt wechselt die Figur bei jedem Schritt das Bild.

---

# Schritt 5: Die Geschwindigkeit anpassen

Die Beine bewegen sich vielleicht viel zu schnell!

- Kategorie `Steuerung`: Setze einen `warte 0.1 Sek.` Block ein.
- **Tipp:** Probiere verschiedene Zahlen aus (z.B. `0.05`), bis das Laufen natürlich aussieht.

---

# Schritt 6: Die Blickrichtung ändern

Die Figur soll immer dorthin schauen, wo sie hinläuft.

- Kategorie `Bewegung`: 
  - Rechts: `setze Richtung auf 90`
  - Links: `setze Richtung auf -90`
- **Hilfe!** Die Figur steht kopf?
  - Klicke bei der Figur auf "Richtung" und wähle **"links/rechts"** (die zwei Pfeile), damit sie nicht rotiert.

---

# Teil 1: Fertig! 🎉

Deine Figur kann nun laufen und sieht dabei lebendig aus!

### Nach der Pause in Teil 2:
- Wir bauen **Schwerkraft** (Gravity).
- Wir lassen die Figur **springen**.

**Gleich geht's weiter!**