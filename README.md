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
