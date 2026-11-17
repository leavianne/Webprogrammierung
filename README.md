# Jahreskalender-PWA für Sachsen

Progressive Web App (PWA) im Fach **Internet-Technologien I** (Beleg SS 2026). Die App berechnet und zeigt einen **Jahreskalender für das Bundesland Sachsen** für die Jahre **2000 bis 2099** an. Umgesetzt mit HTML5, CSS und JavaScript, ohne Frameworks.

## Funktionen

- Anzeige von Jahr, Monaten, Tagen und **Kalenderwochen** (auch wenn eine Woche in zwei Monaten oder zwei Jahren liegt)
- Standardansicht: 12 Monate in 3 Zeilen und 4 Spalten (CSS Grid)
- **Heutiger Tag** wird farblich markiert, wenn das aktuelle Jahr angezeigt wird
- **Feiertage in Sachsen** werden farblich hervorgehoben, per Klick bzw. Touch erscheint der Name
  - statisch: Neujahr, Tag der Arbeit, Tag der deutschen Einheit, Reformationstag, 1. und 2. Weihnachtsfeiertag
  - dynamisch (u. a. per Gaußscher Osterformel berechnet): Karfreitag, Ostermontag, Christi Himmelfahrt, Pfingstmontag, Buß- und Bettag
- Feiertagsdaten im **JSON-Format**, per Ajax aus einer externen Datei geladen
- Ist der heutige Tag kein Feiertag, zeigt ein Klick **fünf berühmte Personen mit Geburtsjahr** (Wikimedia REST API „On this day“, zwischengespeichert im `localStorage`)
- **Topbar** zur Jahresauswahl (Select-Elemente, Standard: aktuelles Jahr), ein- und ausblendbar, mit Button zum Neuladen
- Jahr als Überschrift und im `<title>`
- **Responsives Design** mit Media Queries für Tablet und Handy
- **Installierbar** als PWA (Manifest mit Icons und Service Worker)

## Projektstruktur

| Datei / Ordner | Inhalt |
|---|---|
| `index.html` | Aufbau der Seite |
| `style.css` | Layout, Farben, Media Queries |
| `script.js` | Kalenderberechnung, Feiertage, Wikimedia-API |
| `feiertage.json` | Feiertagsdaten (statisch mit Name, Tag, Monat; dynamisch nur mit Name) |
| `manifest.json` | PWA-Manifest |
| `sw.js` | Service Worker |
| `icons/` | App-Icons |

> Dateinamen bitte an das tatsächliche Repository anpassen.

## Starten

Die App muss über einen Webserver laufen (Service Worker und Ajax funktionieren nicht über `file://`).

1. Ordner mit dem [Simple Web Server](https://simplewebserver.org/download.html) bereitstellen (oder einen anderen lokalen Server verwenden).
2. Die angezeigte Adresse (z. B. `http://localhost:8080`) in **Google Chrome** öffnen.
3. Zum Installieren in der Adressleiste auf das Installationssymbol klicken oder im Chrome-Menü **Streamen, speichern und teilen → App installieren** wählen.

## Technik

- **HTML5, CSS3 (Grid Layout, Media Queries), JavaScript**
- Wikimedia REST API „On this day“ (Geburtstage)
- Web App Manifest und Service Worker
- Getestet mit Google Chrome
