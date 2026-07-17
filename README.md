# onedrive-storage-drilldown

Statische Webseite zum Analysieren der OneDrive-Belegung (TreeSize-ähnlich).

## Verwendung

1. `index.html` lokal oder auf einem statischen Host öffnen.
2. Optional über den **Web-Konfiguration**-Button (Zahnrad) eine eigene Application (Client) ID eintragen. Wenn das Feld leer bleibt, wird die Standard-ID aus `auth-config.js` verwendet.
3. Über **Mit Microsoft anmelden** den Login für die konfigurierte App starten.
4. Für die App-Registrierung (Personal Accounts only) werden die delegierten Microsoft Graph Berechtigungen `User.Read` und `Files.Read` benötigt.
5. In der App-Registrierung die Redirect URI vom Typ **Single-page application (SPA)** auf die URL dieser Seite setzen.
6. Nach dem Redirect auf diese Seite liest die App den `access_token` aus der Redirect-URL (`#access_token=...` oder `?access_token=...`).
7. Optional die **Max. Tiefe** setzen und **Analyse starten** klicken.

Die Seite lädt Client-ID und Tenant-ID aus `auth-config.js` für die hinterlegte App-Registrierung. Diese Werte sind bei einer statischen Webseite clientseitig sichtbar; für die zugehörige App-Registrierung sollten deshalb nur die vorgesehenen Redirect-URIs hinterlegt sein.

## Ergebnis

- Übersicht mit Gesamtspeicher, Anzahl Ordner/Dateien
- Größter Ordner inkl. Pfad
- Größte Datei inkl. Pfad
- Drilldown-Baum bis auf Dateiebene, nach Größe sortiert

## GitHub Pages Deployment (Pipeline)

- Workflow: `.github/workflows/deploy-pages.yml`
- Deployment läuft automatisch bei Push auf `main` (oder manuell via `workflow_dispatch`).
- In den Repository Settings unter **Pages** als Source **GitHub Actions** auswählen.
