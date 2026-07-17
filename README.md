# onedrive-storage-drilldown

Statische Webseite zum Analysieren der OneDrive-Belegung (TreeSize-ähnlich).

## Verwendung

1. `index.html` lokal oder auf einem statischen Host öffnen.
2. Über **Mit Microsoft anmelden** den Login für die in `auth-config.js` hinterlegte Azure-App starten.
3. Nach dem Redirect auf diese Seite liest die App automatisch den `access_token` aus der Redirect-URL (`#access_token=...` oder `?access_token=...`).
4. Alternativ Token manuell einfügen und **Speicher analysieren** klicken.

Die Seite lädt Client-ID und Tenant-ID aus `auth-config.js`. Diese Werte sind bei einer statischen Webseite clientseitig sichtbar; in der Azure-App sollten deshalb nur die vorgesehenen Redirect-URIs hinterlegt sein.

## Ergebnis

- Übersicht mit Gesamtspeicher, Anzahl Ordner/Dateien
- Größter Ordner inkl. Pfad
- Größte Datei inkl. Pfad
- Drilldown-Baum bis auf Dateiebene, nach Größe sortiert

## GitHub Pages Deployment (Pipeline)

- Workflow: `.github/workflows/deploy-pages.yml`
- Deployment läuft automatisch bei Push auf `main` (oder manuell via `workflow_dispatch`).
- In den Repository Settings unter **Pages** als Source **GitHub Actions** auswählen.
