# enclosure/ — Deferred

This folder is reserved for the TACTRACE V1.4 enclosure CAD model and its exported PDFs. **It is intentionally empty in the V1.4 release.**

## Why deferred

The project is transitioning from FreeCAD to **SolidWorks** for parametric mechanical work. The SolidWorks license is pending. Rather than ship a half-converted FreeCAD source or a CAD model that would need to be reworked immediately after import, the V1.4 release documents the enclosure through:

- the engraved **front panel** (photographed in [`../../images/v1_4_front_panel_engraving.jpg`](../../images/v1_4_front_panel_engraving.jpg))
- the engraved **lid quick-reference plate** (art at [`../../images/v1_4_lid_engraving.png`](../../images/v1_4_lid_engraving.png), installed view at [`../../images/v1_4_lid_engraving_installed.jpg`](../../images/v1_4_lid_engraving_installed.jpg))
- the **internal wiring photograph** ([`../../images/v1_4_panel_wiring_underside.jpg`](../../images/v1_4_panel_wiring_underside.jpg))
- the **physical case**: a stock Pelican 1120 (BOM line item #1)

This is enough for a maintainer to **rebuild the V1.4 electrical system** from the schematic and BOM, but it is **not** enough to re-machine an identical enclosure from CAD. That is a known and accepted gap in the V1.4 release, not an oversight.

## What will go here

When the SolidWorks transition is complete, this folder will hold:

- **`*.SLDPRT`** — individual part models (Pelican 1120 panel, lid engraving, mounting brackets if any).
- **`*.SLDASM`** — top-level assembly.
- **`exports/`** — PDF panel-engraving art, dimensioned drawings, and STEP exports for downstream toolchains.

The enclosure update will land as its own commit, tracked in [`../../CHANGELOG.md`](../../CHANGELOG.md), and will not retroactively block the V1.4 release.
