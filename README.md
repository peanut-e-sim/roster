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

Extracted by parallel vision agents, then **every one of the 44 rosters was hand-verified cell-by-cell against its original photo**. Corrections applied:

- 4 May rosters had a day-1 off-by-one (mis-dated to 2025 — all are actually May 2026)
- 1 missed airport code (ICN), 1 spurious code on a continuation cell (idx 32 d1)
- 1 sick/mask icon mis-typed as training
- airport-standby (blue ✓-person) cells distinguished from home standby (idx 17, 11, 41, 43)
- 19 rest-day variant cells (XXR/XXV/XXM) normalized to the green off-arrow shown in the photos

All airport codes and trip structures confirmed. One borderline cell (idx 15 d30, continuation-vs-off) is visually ambiguous in the source photo. Each roster keeps its **"Original photo"** toggle for independent spot-checking.

## ⚠️ Privacy

This repo contains real crew members' flight schedules. **Keep it private.** Do not enable public GitHub Pages or share the source images externally without consent — this is operational data used internally to build the product, consistent with the venture's on-device-only roster principle.
