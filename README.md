# Lern-Apps für die Grundschule

Übersichtsseite unter **https://mitlaeuferfotografie.github.io/**. Sie verlinkt alle öffentlichen Lern-Apps, sortiert nach Fach (Musik, Deutsch, Mathe).

**Grundregel: Jede neue öffentliche Lern-App von mitlaeuferfotografie wird hier eingetragen, sobald sie auf GitHub Pages läuft.**

## Aktuell eingetragene Apps (Stand 14.10.2026)

| Fach | App | Live-Adresse | Repo | Klasse · Thema |
|---|---|---|---|---|
| Musik | Musik-Apps (Sammlung) | /Musik-Apps/ | Musik-Apps | Sammlung · 3 Apps |
| Musik (Unterlink) | Rhythmus-Generator | /Rhythmus-Generator/ | Rhythmus-Generator | – |
| Musik (Unterlink) | Rhythmus-Trainer | /Rhythmus-Trainer/ | Rhythmus-Trainer | – |
| Musik (Unterlink) | Noten-Rätsel | /Noten-Raetsel/ | Noten-Raetsel | – |
| Deutsch | Die Adjektiv-Detektive | /AdjektiveDetektiv/ | AdjektiveDetektiv | Klasse 2 · Adjektive |
| Deutsch | Die große Verben-Expedition | /verben_expedition/ | verben_expedition | Klasse 2 · Verben |
| Deutsch | Die Redezeichen-Helden | /redezeichen-helden/ | redezeichen-helden | Klasse 4 · Wörtliche Rede |
| Deutsch | Pronomen-Magie | /pronomen-magie/ | pronomen-magie | Klasse 4 · Pronomen |
| Mathe | Die Zehner-Bande | /zehner-bande/ | zehner-bande | Klasse 2 · Zahlenraum bis 100 |
| Mathe | Agent M – Math Mission | /MatheAgent/ | MatheAgent | Klasse 4/5 · Knobelaufgaben |

Bewusst **nicht** eingetragen: KI-Werkstatt (Workshop-Seite für Lehrkräfte, keine Kinder-App).
Neue **Musik**-Apps kommen zusätzlich in die Musik-Apps-Übersicht (Repo `Musik-Apps`) und hier als weiterer Unterlink unter der Musik-Karte.

## Aufbau

- `index.html`: die Seite. Ein `<section>`-Block pro Fach (`id="musik"`, `"deutsch"`, `"mathe"`), darin `<div class="cards">` mit einer `<article class="card">` pro App.
- `style.css`: das gesamte Design.
- `impressum.html`: Impressum und Datenschutz (Link im Footer bleibt immer drin).
- `assets/`: Screenshots, 900 × 600 px, JPG (Qualität ca. 84), Dateiname in Kleinbuchstaben mit Bindestrichen.
- GitHub Pages: Branch `main`, Ordner `/ (root)`. Nach einem Push ist die Seite nach ca. 1 Minute aktualisiert.

## Design (nicht ohne Rücksprache ändern)

- Hintergrund `#151515` (sehr dunkles, neutrales Grau) mit leichtem Farbverlauf oben (gelb, rosa, türkis).
- Eine Schriftfamilie: Systemschrift. Keine externen Schriften, CDNs oder Tracking.
- Oben die große Überschrift „Musik. Deutsch. Mathe.“ (die Wörter sind zugleich Sprunglinks).
- Fachfarben nur als Akzent: Musik `#fbbf24`, Deutsch `#fb7185`, Mathe `#2dd4bf`. Sie stehen im Strich unter dem Fachnamen und in der Zeile „Klasse · Thema“.
- Karten mit dezentem Rahmen; beim Überfahren wird der Rahmen weiß, mit weißem Schein und weißem Pfeil.
- Keine Zähler bei den Fächern.
- Sortierung innerhalb eines Fachs: nach Klassenstufe aufsteigend.

## Neue App eintragen: Checkliste

1. **Angaben klären:** Fach, Titel, Live-Adresse, Klassenstufe und Thema. Wenn die Klassenstufe nicht eindeutig aus der App hervorgeht, nachfragen.
2. **Beschreibung:** genau ein Satz, der sagt, was die Kinder in der App tun.
3. **Screenshot** vom Startbildschirm, 900 × 600 px, als `assets/<name>.jpg` (siehe unten).
4. **Karte einfügen:** im passenden Fach-Abschnitt an der richtigen Stelle (nach Klasse sortiert) diese Vorlage einsetzen:

   ```html
   <article class="card">
     <a class="card-link" href="https://mitlaeuferfotografie.github.io/REPO-NAME/">
       <span class="card-media">
         <img src="assets/NAME.jpg" alt="Vorschau der App TITEL" loading="lazy" width="900" height="600">
         <span class="arrow" aria-hidden="true">↗</span>
       </span>
       <span class="card-body">
         <span class="card-meta">Klasse X · Thema</span>
         <span class="card-title">TITEL</span>
         <span class="card-text">Ein Satz, was die Kinder in der App tun.</span>
       </span>
     </a>
   </article>
   ```

5. **Tabelle oben in dieser README** ergänzen.
6. Bei Änderungen an `style.css` die Versionsnummer `style.css?v=…` in `index.html` und `impressum.html` hochzählen (damit Browser die neue Fassung laden).
7. Committen, pushen und nach ca. 1 Minute live prüfen: Karte sichtbar, Bild lädt, Link öffnet die App.

**Neues Fach** (z. B. Sachunterricht): neuen `<section id="…" class="subject t-…">`-Block anlegen, das Wort in der Überschrift ergänzen, eine Akzentfarbe in `style.css` definieren (`--…` und `.t-… { --c: var(--…); }`). Vorher mit der Lehrkraft absprechen.

## Screenshot erstellen

Der Startbildschirm wird in einem 1200 × 800-Fenster aufgenommen und dann auf 900 × 600 verkleinert.

- **Statische App** (nur `index.html`): Repo klonen, Ordner lokal ausliefern (z. B. `python3 -m http.server`) und aufnehmen.
- **React-App** (mit `src/` und `.github/workflows/pages.yml`): so bauen wie im Workflow beschrieben (esbuild-Bundle + Tailwind), dann lokal ausliefern und aufnehmen.
- Aufnahme z. B. mit Playwright/Chromium: Fenster 1200 × 800, Seite laden, ca. 1,5 s warten, Screenshot. Danach mit Pillow auf 900 × 600 verkleinern und als JPG speichern.
- Wenn die App sich im Browser des Rechners öffnen lässt, geht auch ein normaler Screenshot im Format 3:2.
