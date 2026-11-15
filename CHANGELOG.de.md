[English](CHANGELOG.md) | **Deutsch**

# Änderungsprotokoll (Changelog)

Alle wesentlichen Änderungen an **Step Recorder** werden in dieser Datei dokumentiert.

Das Format orientiert sich an [Keep a Changelog](https://keepachangelog.com/de/1.1.0/).

---

## [Unveröffentlicht]

### Hinzugefügt
- **Screenshot-Editor mit 6 Werkzeugen & Farbpalette:** Der integrierte Editor wurde um **Rahmen**, **Pfeil**, **Hinweis** (Textnotiz-Dialog mit optionaler Hinweislinie), **Nummer** (fortlaufende Nummern-Spots `1, 2, 3` per Klick oder als nummerierter Rahmen) und nicht-destruktiven **Zuschnitt** neben **Schwärzen** erweitert – inklusive 4 Markierungsfarben (`#EF4444`, `#2563EB`, `#D97706`, `#16A34A`).
- **Multi-Bereich-Zuschnitt (Collage):** Neuer Toggle **`+ Bereich`** (sowie `Strg+Ziehen` im Zuschnitt-Werkzeug), um mehrere getrennte Bildausschnitte zu markieren; die dunkle Maske im Editor spart alle gewählten Bereiche aus und setzt sie beim Export kompakt als Collage zusammen.
- **Durchgängiges Rückgängig / Wiederholen:** Verlaufssteuerung per `Strg+Z` / `Strg+Y` über Schwärzungen, Markierungen und Zuschnitte hinweg sowie *Zuschnitt aufheben* und *Alle entfernen* pro Schritt.
- **Schritte kombinieren & aufteilen:** Mehrfachauswahl (`Strg` / `Umschalt`) in der Schrittliste, Aktionsleiste, Kontextmenü und Kombinations-Dialog mit zwei Modi:
  - **Überlagern:** Zeichnet die Teilschritte (`a, b, c`) gemeinsam auf ein Basisbild.
  - **Collage:** Ordnet ausgewählte Screenshots mit Ablaufpfeilen nebeneinander an.
- **Umkehrbare Kombination & dynamische Sprache:** Kombinierte Schritttexte (`a) …`, `b) …`) lösen verschachtelte Kombinationen sauber auf, passen nicht manuell editierte Teilschritte bei Sprachwechseln (`de-DE` / `en-US`) automatisch an und lassen sich jederzeit wieder über **Aufteilen** trennen.
- **Rohaufnahmen & Live-Neunummerierung der Badges:** Während der Aufnahme bleiben unannotierte `raw-*.png`-Dateien erhalten, sodass Schritt-Badges beim Umsortieren, Löschen, Kombinieren und Aufteilen automatisch neu gerendert werden.
- **README-Screenshots (`screenshots/`):** Oberfläche im standardmäßigen Hell-Modus, Fenster-/Tab-Auswahl, Einstellungen sowie ergänzend im Dark Mode hinterlegt (`2183a4e`).

### Geändert
- `README.md` und `README.de.md` um alle Editor-Werkzeuge, Multi-Bereich-Zuschnitte, Rückgängig/Wiederholen, Rohaufnahme-Re-Badging sowie Schritt-Kombination und -Aufteilung aktualisiert (`24ef071`).
- `CHANGELOG.md` und `CHANGELOG.de.md` im Repository-Root angelegt.

---

## [1.0.0] - 2026-11-15

Erste öffentliche Veröffentlichung von **Step Recorder (.NET 10 WPF)** (`e4d0114`).

### Hinzugefügt
- **100 % lokal & offline:** Portable Desktop-Anwendung für Windows 10 / 11 (`App/StepRecorder.App.exe`) ohne Cloud-Dienste, Konten oder Telemetrie.
- **Flexible Fenster- & Browser-Auswahl:** Live-Dropdown, visueller **Fenster-Browser** (gruppiert nach Programm mit Live-Vorschau, Suche und Wiederherstellung minimierter Fenster) sowie **Fenster per Klick wählen** (`Esc` oder Rechtsklick zum Abbruch).
- **Browser-Erkennung & Tab-Fixierung:** Unterstützung für Chromium (`chrome`, `msedge`, `brave`, `vivaldi`, `opera`, `arc`, `chromium`, `thorium`, `sidekick`) und Gecko (`firefox`, `librewolf`, `waterfox`, `floorp`, `zen`), Option **Nur Seiteninhalt** sowie **Tab-Fixierung** inklusive automatischer Pause und Warn-Badge bei Tab-Wechsel.
- **Intelligente Eingabe-Erkennung & UIA3-Textbildung:** Linksklicks, automatische Doppelklick-Zusammenführung (Windows-Doppelklickzeit + 6 px Radius), Rechtsklicks, zusammengefasste Texteingaben (900 ms Debounce mit `AltGr`-Unterstützung), Aufwertung von Klicks in `Edit`-/ `ComboBox`-Felder sowie Passwortschutz über `IsPassword`.
- **Automatische Annotationen & Schwärzung:** Element-Hervorhebungsrahmen, Klick-Marker und Schritt-Badges sowie aufziehbare Schwärzungsrechtecke (via SkiaSharp beim Export eingebrannt).
- **Schritt-Editor & getrennte UI-/Anleitungssprache (`de-DE` / `en-US`):** Bearbeitung von Anleitungstitel und Schritttexten (inkl. Zurücksetzen auf Auto-Text), Umsortierung (Hoch/Runter), Löschen mit automatischer Neunummerierung, Sitzung leeren sowie unabhängige Umschaltung von Programmoberfläche und Anleitungssprache zur Laufzeit.
- **Eigenständiger HTML- & A4-PDF-Export:** Offlinefähige Einzeldatei-`.html` (Base64-PNGs, deduplizierte klickbare Seiten-URLs, Lightbox-Zoom) und mehrseitiges A4-`.pdf` (Standardordner `%USERPROFILE%\Downloads`).
- **Moderne Windows-Oberfläche:** `PerMonitorV2`-DPI-Unterstützung, Design-Modi (`System`, `Hell`, `Dunkel`, Windows-Hochkontrast), lokale Einstellungen unter `%LOCALAPPDATA%\StepRecorder\settings.json`, temporäre Sitzungsdaten in `%TEMP%\StepRecorder\Sessions\` und ein schwebendes **Aufnahme-HUD** (aus Screenshots ausgeblendet).
- **Dokumentation & Lizenzen:** Englische und deutsche README (`README.md`, `README.de.md`), `LICENSE` (MIT), `LICENSE.de.md` (deutsche Übersicht & Drittanbieter-Hinweise) sowie `.gitignore`.
