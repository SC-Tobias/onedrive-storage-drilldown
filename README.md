# onedrive-storage-drilldown

Statische Webseite zum Analysieren der OneDrive-Belegung (TreeSize-ähnlich).

## Verwendung

1. `index.html` lokal oder auf einem statischen Host öffnen.
2. Microsoft OAuth so konfigurieren, dass der Redirect auf diese Seite zeigt.
3. Die Seite liest automatisch `access_token` aus der Redirect-URL (`#access_token=...` oder `?access_token=...`).
4. Alternativ Token manuell einfügen und **Speicher analysieren** klicken.

## Ergebnis

- Übersicht mit Gesamtspeicher, Anzahl Ordner/Dateien
- Größter Ordner inkl. Pfad
- Größte Datei inkl. Pfad
- Drilldown-Baum bis auf Dateiebene, nach Größe sortiert

## GitHub Pages Deployment (Pipeline)

- Workflow: `.github/workflows/deploy-pages.yml`
- Deployment läuft automatisch bei Push auf `main` (oder manuell via `workflow_dispatch`).
- In den Repository Settings unter **Pages** als Source **GitHub Actions** auswählen.
