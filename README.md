# Crew Roster Visualizer

Reconstruction of **44 Emirates "Crew Pulse" rosters** (May / June 2026) collected for building Peanut eSIM's Schedule-Upload OCR feature.

Each roster is a phone photo of a crew member's monthly calendar. Every photo was read cell-by-cell (vision OCR) and re-rendered as a clean native calendar — flights + airport codes, days off, standby, training, leave, and airport-standby (ASBY). The destinations that actually need eSIM data (home base **DXB** excluded) are derived per roster and aggregated into a demand signal.

## View

Open **`index.html`** in a browser. Self-contained (data embedded); the per-roster "Original photo" toggle loads the source images from `2026-06-09-akito/` and `2026-06-10-akito/`.

## Contents

| Path | What |
|------|------|
| `index.html` | The visualizer (all 44 rosters + master intel panel + month filter) |
| `data/rosters.json` | Structured extraction (month, year, per-day type/code/color) |
| `2026-06-09-akito/` | 25 source roster photos |
| `2026-06-10-akito/` | 19 source roster photos |

## Aggregate signal

- **44 rosters** · May 2026 (23), June 2026 (21)
- **93 unique destinations** across **241 outstation legs**
- Top demand: MXP, JFK, DMM, JNB, HND, CAI, LHE …

## Accuracy

Extracted by parallel vision agents, then **audited cell-by-cell against the originals** by an independent second pass. Corrections applied: 4 May rosters had a day-1 off-by-one (mis-dated to 2025 — all are 2026), one missed airport code (ICN), one sick-icon mis-typed as training, and airport-standby cells distinguished from home standby. Continuation (no-code) trip cells verified. Residual risk: a stray airport-code misread is possible across 241 legs — each roster has its original-photo toggle for spot-checking.

## ⚠️ Privacy

This repo contains real crew members' flight schedules. **Keep it private.** Do not enable public GitHub Pages or share the source images externally without consent — this is operational data used internally to build the product, consistent with the venture's on-device-only roster principle.
