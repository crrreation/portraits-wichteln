# Portraits Wichteln

Website fürs Portrait-Wichteln: Countdown bis zur Auslosung, Anmeldung per E-Mail und Galerie mit den Portraits der Vorjahre.

- **Keine Datenbank, kein Server, kein Google.** Die Seite ist rein statisch (GitHub Pages).
- **Anmeldung:** Name und E-Mail eingeben, «Anmelden» öffnet eine fertige E-Mail an `maggie.blaser@digitecgalaxus.ch`. Wer sie abschickt, ist dabei. Funktioniert auch für Externe.
- **Auslosung und Versand:** am 1. Dezember lokal auf dem Mac mit der Datei `Wichtel-Versand.html` (liegt nicht in diesem Repo, sondern nur auf dem Mac im Ordner `Claude/Portraits Wichteln`). Die Mails gehen über Outlook im Browser raus.

---

## 1. Auf GitHub veröffentlichen

1. Auf github.com im Konto/der Organisation **crrreation** → **New repository**.
2. Name: `portraits-wichteln`, Sichtbarkeit **Public** → **Create repository**.
3. **uploading an existing file** → alle Dateien und Ordner aus diesem Paket hineinziehen (`index.html`, `gallery.json`, `README.md`, `assets/`, `bilder/`, `fonts/`) → **Commit changes**.
4. **Settings → Pages** → Source **Deploy from a branch**, Branch **main**, Ordner **/ (root)** → **Save**.
5. Nach 1–2 Minuten ist die Seite erreichbar unter `https://crrreation.github.io/portraits-wichteln/`. Diesen Link verschickst du ans Team und an Externe.

## 2. Einstellungen in `index.html`

Oben im Skript (direkt nach `<script>`) stehen diese Zeilen:

```js
const ANMELDE_MAIL = 'maggie.blaser@digitecgalaxus.ch';            // an diese Adresse gehen die Anmeldungen
const RUNDE = { year: 2026, opensAt: '2026-12-01T00:00:00+01:00' }; // Jahr und Zeitpunkt der Auslosung
```

Für nächstes Jahr nur `year` und das Datum anpassen.

## 3. Anmeldungen sammeln

- Anmeldungen kommen als Mails mit dem Betreff **«Anmeldung Portraits Wichteln 2026»** in das Postfach von maggie.blaser@digitecgalaxus.ch.
- Tipp: In Outlook eine Regel anlegen, die diese Mails in einen eigenen Ordner verschiebt.
- Kopiere den Text der Anmelde-Mails in `Wichtel-Versand.html` ins Feld «Anmelde-Mails einfügen» → «In die Liste übernehmen». Name und E-Mail werden automatisch erkannt, doppelte übersprungen. Die Liste wird dort gespeichert.

## 4. Am 1. Dezember: auslosen und Mails verschicken

1. `Claude/Portraits Wichteln/Wichtel-Versand.html` auf dem Mac doppelklicken (öffnet im Standardbrowser). Im selben Browser muss Outlook (outlook.office.com) angemeldet sein.
2. Liste prüfen → **Auslosen**. Niemand bekommt sich selbst.
3. Bei jeder Person **In Outlook öffnen** → im neuen Tab auf **Senden** klicken. Die Zeile wird als erledigt markiert.
4. Zur Sicherheit **Ergebnis als Datei sichern** (CSV mit der Zuordnung, bleibt auf dem Mac).

Wichtig: Immer denselben Browser auf demselben Mac verwenden, denn die Liste ist im Browser gespeichert. Die gesicherte CSV-Datei ist das Backup.

## 5. Galerie pflegen

1. Fotos in `bilder/<jahr>/` hochladen, z. B. `bilder/2026/annina-1.jpg` (JPG, max. ca. 1000 px hoch).
2. In `gallery.json` pro Bild einen Eintrag ergänzen:
   ```json
   { "year": 2026, "giver": "", "receiver": "Annina", "bild": "bilder/2026/annina-1.jpg" }
   ```
   `receiver` ist die porträtierte Person, daraus wird «Anninas Portrait 2026». Zwischen Einträgen ein Komma, nach dem letzten keins.
3. Die Reihenfolge wird pro Jahr gemischt, Portraits derselben Person stehen nebeneinander.

## 6. Schrift

Europa / ET Galaxus wird verwendet, wenn auf dem Gerät installiert oder als `fonts/Europa-Bold.woff2` und `fonts/Europa-Light.woff2` abgelegt (nur wenn die Lizenz die Einbettung auf einer öffentlichen Website erlaubt). Sonst erscheint **Jost** (freie Schrift, Lizenz liegt in `fonts/`), ebenfalls mit einstöckigem «a».

---

## Gut zu wissen

- **Datenschutz:** Die Website speichert nichts. E-Mail-Adressen liegen nur im Postfach von maggie.blaser@digitecgalaxus.ch und lokal auf dem Mac.
- **Wer verschickt, sieht die Zuordnung** beim Öffnen der Mails in Outlook. Die Versand-Seite blendet sie sonst aus.
- **Spam:** Mails an externe Adressen können im Spam landen. Am besten vorher ankündigen.
