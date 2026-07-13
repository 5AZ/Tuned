# Changelog

Notable changes to Tuned, newest first.

## v0.3.0 — 2026-07-12

- Feat: thermal-aware tray icon — the pulse glyph shifts amber → yellow → red as the hottest of CPU, GPU or disk crosses 60 °C and 80 °C, so a hot system reads from the tray without opening the window.
- Feat: remember window size, position and the last-viewed tab between sessions, recentring automatically if the saved placement lands off-screen.
- Fix: restoring from the tray no longer reappears minimised — the window comes back at its proper size and takes focus.

## v0.2 — 2026-07-09

- First public release: portable, tray-resident hardware monitor with a Now view (hero tiles, per-core heat grid, sparklines, live top processes) and a History view (stacked lanes over 15m–7d, synced crosshair, top offenders).
