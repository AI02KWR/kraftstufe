Dieses Verzeichnis enthält meine Fitness-App „Kraftstufe“ als fertige PWA (siehe CLAUDE.md).
Bitte bring sie auf GitHub und mach sie über GitHub Pages erreichbar, damit ich sie auf meinem
iPhone über „Zum Home-Bildschirm“ installieren kann.

Schritte:
1. Prüfe, ob `git` und die GitHub CLI (`gh`) installiert sind und ich mit `gh auth status`
   angemeldet bin. Falls nicht, erkläre mir kurz, was ich tun muss (z. B. `gh auth login`), und warte.
2. Starte lokal `python3 -m http.server 8000` und prüfe, dass `index.html`, `manifest.webmanifest`,
   `sw.js` und alle Dateien in `icons/` ohne Fehler ausgeliefert werden. Beende den Server danach.
3. Initialisiere ein Git-Repository mit dem Branch `main`, committe alle Dateien
   (Nachricht: „Kraftstufe PWA“).
4. Lege mit `gh repo create kraftstufe --public --source=. --push` ein öffentliches Repository an.
   (GitHub Pages ist bei kostenlosen Konten nur für öffentliche Repos verfügbar.)
5. Aktiviere GitHub Pages mit „GitHub Actions“ als Quelle:
   `gh api -X POST repos/{owner}/kraftstufe/pages -f build_type=workflow`
   (falls es schon existiert: dasselbe mit `-X PUT`).
6. Warte, bis der Workflow „Deploy to GitHub Pages“ durchgelaufen ist (`gh run watch`), und
   prüfe mit `curl -I`, dass die Seite mit Status 200 erreichbar ist.
7. Gib mir am Ende die fertige URL und eine kurze Anleitung, wie ich die App in Safari über
   „Teilen → Zum Home-Bildschirm“ installiere.

Ändere dabei nichts an der App selbst, außer ein Schritt schlägt wegen eines Fehlers in den
Dateien fehl. Dann erkläre mir vorher, was du ändern möchtest.
