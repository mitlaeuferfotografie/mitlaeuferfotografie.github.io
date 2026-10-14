# Lern-Apps für die Grundschule

Übersichtsseite unter **https://mitlaeuferfotografie.github.io/** mit Links zu allen öffentlichen Lern-Apps, sortiert nach Fach (Musik, Deutsch, Mathe).

- Reines HTML/CSS, kein Build-Schritt, keine externen Ressourcen (nur Systemschriften, keine CDNs, kein Tracking).
- Screenshots in `assets/` (900 × 600 px, JPG) zeigen den Startbildschirm der jeweiligen App (Stand: 14.10.2026).
- GitHub Pages: Branch `main`, Ordner `/ (root)`.

## Neue App ergänzen
1. Screenshot als `assets/<name>.jpg` (3:2) ablegen.
2. In `index.html` im passenden Fach-Abschnitt eine `<article class="card">` kopieren und Link, Bild, die Zeile „Klasse · Thema“, Titel und den einen Beschreibungssatz anpassen.
3. Für ein neues Fach: neuen `<section>`-Block, Eintrag in der Sprungleiste (`.jump`) und eine Farbe in `style.css` (`--neuesfach`, `.subject-neuesfach`).
