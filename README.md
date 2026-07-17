# onedrive-storage-drilldown

Statische Webseite zum Analysieren der OneDrive-Belegung (TreeSize-ähnlich).

## Verwendung

1. `index.html` lokal oder auf einem statischen Host öffnen.
2. Über **Mit Microsoft anmelden** den Login für die in `auth-config.js` hinterlegte Enterprise-App starten.
3. Nach dem Redirect auf diese Seite liest die App den `access_token` aus der Redirect-URL (`#access_token=...` oder `?access_token=...`).
4. Optional die **Max. Tiefe** setzen und **Analyse starten** klicken.
5. Bei Einträgen mit **(nicht weiter analysiert)** kann pro Ordner über **Mehr laden** eine tiefere Analyse für genau diesen Bereich nachgeladen werden.

Die Seite lädt Client-ID und Tenant-ID aus `auth-config.js` für die hinterlegte Enterprise-App. Diese Werte sind bei einer statischen Webseite clientseitig sichtbar; für die zugehörige App-Registrierung sollten deshalb nur die vorgesehenen Redirect-URIs hinterlegt sein.

## Ergebnis

- Übersicht mit Gesamtspeicher, Anzahl Ordner/Dateien
- Größter Ordner inkl. Pfad
- Größte Datei inkl. Pfad
- Drilldown-Baum bis auf Dateiebene, nach Größe sortiert

## GitHub Pages Deployment (Pipeline)

- Workflow: `.github/workflows/deploy-pages.yml`
- Deployment läuft automatisch bei Push auf `main` (oder manuell via `workflow_dispatch`).
- In den Repository Settings unter **Pages** als Source **GitHub Actions** auswählen.
