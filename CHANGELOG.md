**English** | [Deutsch](CHANGELOG.de.md)

# Changelog

All notable changes to **Step Recorder** are documented in this file.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

---

## [Unreleased]

### Added
- **6-Tool Screenshot Editor & Color Palette:** Expanded the built-in image editor beyond **Redact** rectangles with **Box** (highlight frames), **Arrow** (directional arrows), **Note** (callout dialog with optional pointer line), **Spot** (sequential numbered badges `1, 2, 3` dropped by click or dragged as a numbered highlight box), and non-destructive **Crop**, plus 4 accent color swatches (`#EF4444`, `#2563EB`, `#D97706`, `#16A34A`).
- **Multi-Region Crop Cutout Collage:** Added the **`+ Region`** toggle (and `Ctrl+Drag` shortcut in Crop mode) to select multiple non-overlapping regions on a screenshot, displaying a live dark union cutout mask in the editor and stitching them into a clean cutout collage on export.
- **Unified Per-Step Undo / Redo:** Added `Ctrl+Z` / `Ctrl+Y` undo and redo history across redactions, annotations, and crops, plus one-click *Reset Crop* and *Clear All*.
- **Step Combining & Splitting:** Added extended multi-selection (`Ctrl` / `Shift`) in the step list, selection action strip, context menu, and combine modal dialog with two output modes:
  - **Overlay:** Draws sub-step markers (`a, b, c`) onto one shared screenshot.
  - **Collage:** Arranges selected step screenshots side by side with flow arrows.
- **Reversible Combined Steps & Live Language Updates:** Combined steps format sub-steps cleanly as `a) …`, `b) …`, flatten nested combinations, regenerate unedited sub-steps dynamically on guide language switches (`de-DE` / `en-US`), and can be **Split** back into individual steps at any time.
- **Raw Capture Archival & Live Badge Re-Rendering:** Sessions now preserve unannotated `raw-*.png` captures alongside annotated screenshots so step number badges re-render cleanly whenever steps are moved up/down, deleted, combined, or split.
- **README UI Screenshots (`screenshots/`):** Added light-default workspace, window/tab browser, and settings screenshots alongside a supplementary dark-mode view (`2183a4e`).

### Changed
- Updated `README.md` and `README.de.md` to reflect all screenshot editor tools, multi-region cutout collages, undo/redo, live badge re-rendering, and step combining/splitting (`24ef071`).
- Added `CHANGELOG.md` and `CHANGELOG.de.md` at the repository root.

---

## [1.0.0] - 2026-11-15

Initial public release of **Step Recorder (.NET 10 WPF)** (`e4d0114`).

### Added
- **100% Local & Offline Architecture:** Portable Windows 10 / 11 desktop application (`App/StepRecorder.App.exe`) with zero cloud dependencies, accounts, or telemetry.
- **Flexible Window & Browser Targeting:** Live target window dropdown, grouped visual **Window Browser** (with live preview thumbnails, search, and minimized-window restore), and global **Click-to-Pick** (`Esc` or right-click to cancel).
- **Browser-Aware Capture & Tab Locking:** Supports Chromium (`chrome`, `msedge`, `brave`, `vivaldi`, `opera`, `arc`, `chromium`, `thorium`, `sidekick`) and Gecko (`firefox`, `librewolf`, `waterfox`, `floorp`, `zen`) browsers, optional **Page Content Only** viewport cropping, and **Single-Tab Pinning** with automatic pause and warning badge on tab switch.
- **Smart Input Capture & UIA3 Step Descriptions:** Left-click capture, automatic double-click merging (Windows double-click interval + 6 px radius), right-clicks, debounced 900 ms text-input bursts with `AltGr` support, automatic upgrade of clicks in `Edit` / `ComboBox` controls into text steps, and password field protection (`IsPassword`).
- **Automatic Annotations & Redaction Editor:** Automatic element highlight frames, click markers, and step badges with drag-to-redact black rectangles flattened into exports via SkiaSharp.
- **Post-Recording Step Editor & Bilingual Runtime (`de-DE` / `en-US`):** Guide title editing, manual step description editing with one-click reset, step reordering (Up / Down), deletion with automatic renumbering, session reset, and independent runtime switching of UI and guide languages.
- **Self-Contained HTML & Multi-Page A4 PDF Export:** Offline single-file `.html` (Base64 PNG screenshots, deduplicated clickable URLs, lightbox zoom) and multi-page A4 `.pdf` saved to `%USERPROFILE%\Downloads` by default.
- **Adaptive Windows UI:** `PerMonitorV2` DPI awareness, `System` / `Light` / `Dark` / Windows High-Contrast theme modes, local JSON settings in `%LOCALAPPDATA%\StepRecorder\settings.json`, temporary session files in `%TEMP%\StepRecorder\Sessions\`, and always-on-top **Recording HUD** excluded from screenshots.
- **Documentation & Licensing:** English and German READMEs (`README.md`, `README.de.md`), `LICENSE` (MIT), `LICENSE.de.md` (German summary & third-party notices), and `.gitignore`.
