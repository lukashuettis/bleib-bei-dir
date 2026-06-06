# Bleib bei dir 🌿

Eine kleine, sanfte **Trigger-Begleiter-PWA**. Wenn dich etwas triggert, tippst du kurz drauf – es wird lokal festgehalten und du bekommst eine kurze Mutmach-Botschaft mit einer Atemübung. Maskottchen: **Beni**.

- **100 % lokal & privat** – alle Daten liegen nur im Browser des Geräts (`localStorage`). Nichts geht ins Internet, keine Accounts, keine Tracker, keine externen Netzwerk-Aufrufe.
- **Offline-fähig** – funktioniert nach dem ersten Laden auch ohne Netz (Service Worker).
- **Installierbar** – „Zum Home-Bildschirm" hinzufügen → eigenes App-Icon, Vollbild.

## Funktionen

- **Jetzt** – große Trigger-Buttons. Tippen → Eintrag + Mutmach-Popup mit Atem-Ring.
- **Verlauf** – Statistik (heute / 7 Tage / gesamt), Balken pro Trigger, letzte Einträge (einzeln löschbar).
- **Trigger** – eigene Trigger anlegen / umbenennen / Farbe & Emoji wählen / löschen.

Die vier Start-Trigger (Kritik, Vergleich, Social Media, Zurückweisung) sind nur Vorschläge und lassen sich jederzeit anpassen.

## Dateien

```
index.html              ← die ganze App (HTML + CSS + JS in einer Datei)
manifest.webmanifest    ← PWA-Manifest (App-Name, Icons, Farben)
sw.js                   ← Service Worker (Offline-Cache)
robots.txt              ← hält Suchmaschinen-Crawler fern
icons/                  ← App-Icons (PNG) + Quell-SVG
```

## Lokal testen

```bash
cd bleib-bei-dir
python3 -m http.server 8080
# Browser: http://localhost:8080
```

## Deployen

Statische Seite – kein Build nötig. Drei einfache Wege:

### Option A – Netlify Drop (am schnellsten)
1. <https://app.netlify.com/drop> öffnen.
2. Den **gesamten Ordner** ins Browserfenster ziehen.
3. Sofort eine HTTPS-URL. Optional mit kostenlosem Account dauerhaft sichern.

### Option B – GitHub Pages
1. Repo anlegen, Ordnerinhalt pushen.
2. Repo → **Settings → Pages → Branch: `main`, Ordner: `/ (root)`** → Save.

### Option C – Vercel
1. <https://vercel.com> → „Add New… → Project" → importieren → Deploy.

## Installation aufs Handy

**iPhone (Safari):** Link in **Safari** öffnen → Teilen-Symbol → **„Zum Home-Bildschirm"**.

**Android (Chrome):** Link in **Chrome** öffnen → Menü (⋮) → **„App installieren"** / „Zum Startbildschirm hinzufügen".

> Nach dem ersten Öffnen läuft die App auch komplett offline.

## Sichtbarkeit / Suchmaschinen

`robots.txt` und ein `noindex`-Meta-Tag halten Suchmaschinen-Crawler fern, damit die Seite nicht in Web-Suchergebnissen auftaucht. (Wer die direkte URL kennt, kann sie weiterhin öffnen.)

## Daten / Privatsphäre

Es werden **keine** Daten an einen Server gesendet. Alles bleibt auf dem Gerät. Wird die App deinstalliert oder der Browser-Speicher der Seite gelöscht, sind die Einträge weg (so gewollt – maximale Privatsphäre).
