---

marp: true
theme: gaia
paginate: true

style: |
  :root {
    --color-background: #111318;
    --color-foreground: #e7e9ee;
    --color-highlight: #a99cff;
    --color-highlight-hover: #c9bfff;
    --color-highlight-heading: #c9bfff;
    --color-header: #737985;
    --color-footer: #737985;
  }

  section {
    background-color: #111318;
    color: #e7e9ee;
    font-family: "Helvetica Neue", Arial, sans-serif;
    padding: 42px 56px;
    font-size: 27px;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  h1 {
    color: #c9bfff;
  }

  h2 {
    color: #ffffff;
  }

  h3 {
    color: #d7d9e0;
  }


  section.title {
  text-align: center;
  }

  strong {
    color: #ffb45c;
  }

  blockquote {
    background: #1b1e26;
    border-left: 5px solid #8f7cff;
    color: #f2f3f7;
    border-radius: 8px;
    padding: 14px 20px;
  }

  code {
    background: #252934;
    color: #ffc978;
    padding: 2px 6px;
    border-radius: 5px;
  }

  pre {
    background: #090b0f;
    color: #e8e8e8;
    border: 1px solid #292d38;
    border-radius: 10px;
    padding: 17px 20px;
    font-size: 0.72em;
  }

  pre code {
    background: transparent;
    color: inherit;
  }

  .box {
    background: #1a1d24;
    border: 1px solid #30343f;
    border-radius: 10px;
    padding: 14px 18px;
    margin: 14px 0;
  }

  section.chapter {
    background: #16131f;
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  section.chapter h1 {
    color: #ffffff;
    font-size: 2.2em;
  }

  section.chapter h2 {
    color: #a99cff;
  }

  section.title {
    background: #0b0d12;
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  section.title h1 {
    color: #ffffff;
    font-size: 2.35em;
  }

  section.title h2 {
    color: #a99cff;
  }

---

<!-- _class: title -->
<!-- _paginate: false -->

# Scratch Workshop

## Teil 2 · Variablen & Broadcast

**Fortgeschrittene Konzepte**

<small>Nobu · Scratch - Einstieg ins Gameprogrammieren</small>

---

# Rückblick

Im ersten Teil habt ihr gelernt:

* Sprites bewegen
* Hintergründe wechseln
* Dialoge verwenden
* Blöcke kombinieren

---

# Ziel für diesen Part

<div class="box">

**Variablen**

Wie kann Scratch Informationen speichern?

</div>

<div class="box">

**Broadcast**

Wie können Figuren miteinander kommunizieren?

</div>

---

<!-- _class: chapter -->

# Teil A

## Variablen

Merken · Verändern · Rechnen

---

# Was ist eine Variable?

> Eine Variable ist wie eine **Box mit einem Namen**.

In dieser Box kann Scratch einen Wert speichern.

Zum Beispiel:

* Punkte, Highscore
* Namen, Textstring
* Zeit

---

# Beispiele für Variablen

### Punkte

`Punkte = 12`

### Namen, Texte

`Text = "Scratch is toll"`

### Zeit

`Zeit = 45`

<div class="box">

Der Wert kann sich während des Spiels verändern.

</div>

---

# Variable erstellen

1. Öffne **Variablen**.
2. Klicke auf **„Variable erstellen“**.
3. Gib ihr einen Namen.

Zum Beispiel:

`Punkte`

oder

`Text`

---

# Für wen gilt die Variable?

Scratch fragt:

**Für alle Figuren?**

oder

**Nur für diese Figur?**

<div class="box">

Für Punkte oder Zeit ist meistens
**„für alle Figuren“** sinnvoll.

</div>

---

# Wert setzen

```text id="bnq8dh"
set [Punkte v] to [0]
```

Damit bekommt die Variable einen Startwert.

Zum Beispiel beim Start des Spiels:

```text id="eotbsr"
[Grüne Flagge angeklickt]

set [Punkte v] to [0]
```

---

# Wert verändern

```text id="0zjaxc"
change [Punkte v] by [1]
```

Dadurch wird:

`0 → 1 → 2 → 3 → ...`

<div class="box">

Mit `-1` kann man einen Wert auch verringern.

</div>

---

# Wert benutzen

Der runde Block

```text id="69jj8n"
(Punkte)
```

liefert den aktuellen Wert.

Damit können wir zum Beispiel prüfen:

```text id="ucjq6k"
if <(Punkte) = [10]> then
```

---

# Beispiel: Klick-Spiel

```text id="p6y3j1"
[Grüne Flagge angeklickt]

set [Punkte v] to [0]

forever
  if <Mauszeiger berührt?> then
    change [Punkte v] by [1]
  end
end
```

---

# Kleine Herausforderung

Wie könnte man verhindern, dass ein Klick sofort viele Punkte gibt?

<div class="box">

Tipp:

```text id="dq7ix8"
wait (0.2) seconds
```

</div>

---

<!-- _class: chapter -->

# Teil B

## Broadcast

Nachrichten zwischen Figuren

---

# Warum Broadcast?

Stellt euch vor:

**Katze erreicht das Ziel.**

Der Hund soll darauf reagieren.

Aber woher weiss der Hund, dass das Ziel erreicht wurde?

---

# Die Idee

> Ein Broadcast ist wie eine **Durchsage**.

Eine Figur sendet eine Nachricht.

Andere Figuren können auf diese Nachricht reagieren.

---

# Nachricht senden

Unter **Ereignisse** findet ihr:

```text id="xlfjla"
broadcast [SpielStart v]
```

Die Figur sendet damit die Nachricht:

**„SpielStart“**

---

# Nachricht empfangen

Eine andere Figur kann darauf warten:

```text id="nwgzip"
when I receive [SpielStart v]
```

Danach führt sie ihre eigenen Blöcke aus.

---

# Beispiel: Spielstart

Start-Button wird geklickt.

```text id="pqtqbq"
broadcast [SpielStart v]
```

Danach können mehrere Figuren gleichzeitig reagieren.

---

# Beispiel: Levelwechsel

Eine Figur erreicht das Ziel.

```text id="h9a5ae"
broadcast [Nächstes Level v]
```

Danach könnte:

* der Hintergrund wechseln
* ein Gegner erscheinen
* die Geschwindigkeit steigen

---

# Beispiel: Dialog

### Katze

```text id="5fnu0r"
[Grüne Flagge angeklickt]

say [Hallo Hund!] for (2) secs

broadcast [Antworten v]
```

---

# Der Hund antwortet

```text id="k48jip"
when I receive [Antworten v]

say [Wuff! Hallo!] for (2) secs
```

<div class="box">

Die Nachricht startet das Skript des Hundes.

</div>

---

<!-- _class: chapter -->

# Beide Konzepte zusammen

## Variable + Broadcast

---

# Beispiel: Gewonnen!

Wir prüfen zuerst die Punkte:

```text id="jevifj"
if <(Punkte) = [10]> then

  broadcast [Gewonnen v]

end
```

---

# Auf „Gewonnen“ reagieren

Eine andere Figur könnte dann:

```text id="93aqbj"
when I receive [Gewonnen v]

say [Du hast gewonnen!] for (2) secs
```

Oder der Hintergrund wechselt zum Gewinner-Bildschirm.

---

# Zusammenfassung

<div class="box">

**Variable**

Das **Gedächtnis** des Programms.

</div>

<div class="box">

**Broadcast**

Die **Kommunikation** zwischen Figuren.

</div>

---

<!-- _class: chapter -->

# Jetzt seid ihr dran

