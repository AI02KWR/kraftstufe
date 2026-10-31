# Kraftstufe – Projektkontext für Claude Code

Kraftstufe ist eine Fitness-Web-App (Progressive Overload, Push Pull Legs, XP, Ränge) als
installierbare PWA. Sie wird über GitHub Pages gehostet und auf dem iPhone über
„Zum Home-Bildschirm“ wie eine App genutzt.

## Aufbau
- `index.html` – die komplette App (HTML, CSS und JavaScript in einer Datei, kein Build-Schritt)
- `manifest.webmanifest` – App-Name, Farben, Icons
- `sw.js` – Service Worker für Offline-Betrieb
- `icons/` – App-Icons (180, 192, 512, maskable 512)
- `.github/workflows/pages.yml` – automatisches Deployment auf GitHub Pages bei jedem Push auf `main`

## Regeln
- Kein Build-Tool, keine Frameworks einführen. Die App bleibt eine einzelne `index.html`.
- Daten liegen in `localStorage` (Schlüssel `kraftstufe-data`, Entwurf in `kraftstufe-draft`).
  Das Datenformat nie inkompatibel ändern, sonst gehen Trainings der Nutzer verloren.
- Nach jeder Änderung an `index.html` die Konstante `VERSION` in `sw.js` erhöhen
  (z. B. `kraftstufe-v1` → `kraftstufe-v2`), damit iPhones die neue Version laden.
- Alle Texte in der App auf Deutsch.
- Lokal testen mit `python3 -m http.server 8000` und http://localhost:8000 öffnen.
