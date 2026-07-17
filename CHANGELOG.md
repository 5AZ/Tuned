# Changelog

Notable changes to Tuned, newest first.

## v0.5.0 — 2026-07-17

- Feat: the DISK and FAN tiles now open a source menu on click (auto plus every detected drive/fan with its live readings, a check on the current choice) instead of blind cycling. The tile header shows one dot per source with the displayed one lit, and a pin glyph that saturates when a source is pinned; both hide when there is only one source. Everything detected is always logged, so switching sources shows full history immediately.
- Feat: the Activity lanes render sizeable data gaps (app closed, machine asleep) as a thin dashed link between the last and next real samples instead of a smooth solid line that implied data existed. The min/max band also stops at gap edges, gaps too small to convey anything keep the solid join, and the crosshair readout shows a dash inside a rendered gap rather than quoting a value the machine never produced.

## v0.4.0 — 2026-07-16

- Feat: warning-free disk monitoring under Windows Defender's Controlled Folder Access. Tuned detects when CFA would flag its disk access as ransomware-like ("blocked from making changes to memory") and switches to read-only collection: every drive's activity and NVMe temperatures still flow, with no Defender toast. HDD (SMART) temperatures need a Defender allow-list entry, and the footer and DISK tile tooltip say so. The README's "A note on Windows Defender and disk sensors" section tells the story.
- Feat: the DISK tile names the drive it is showing and click-cycles between drives (auto follows the hottest); the FAN tile does the same for fans (auto follows the fastest). The Activity lanes follow the pinned choice and carry the drive/fan name in their titles. Display only: everything detected is always logged.
- Feat: the autostart toggle now verifies the scheduled task is enabled and points at an executable that exists, instead of only checking the task name. A moved portable install self-heals at launch (the task is re-registered against the running copy) with a brief footer notice.
- Fix: restoring the window onto the Activity tab no longer shows the "data being collected" placeholder until a tab switch; lanes now build as soon as sensors finish enumerating.

## v0.3.1 — 2026-07-14

- Feat: the status footer (live dot, sensor count, database size, elevation and the autostart toggle) now sits beneath both tabs instead of only the first view, so it stays put when switching between them.
- Feat: the version badge links to the project on GitHub.
- Change: renamed the tabs from Now / History to **Live / Activity**; Live remains the default view.

## v0.3.0 — 2026-07-12

- Feat: thermal-aware tray icon — the pulse glyph shifts amber → yellow → red as the hottest of CPU, GPU or disk crosses 60 °C and 80 °C, so a hot system reads from the tray without opening the window.
- Feat: remember window size, position and the last-viewed tab between sessions, recentring automatically if the saved placement lands off-screen.
- Fix: restoring from the tray no longer reappears minimised — the window comes back at its proper size and takes focus.

## v0.2 — 2026-07-09

- First public release: portable, tray-resident hardware monitor with a Now view (hero tiles, per-core heat grid, sparklines, live top processes) and a History view (stacked lanes over 15m–7d, synced crosshair, top offenders).
