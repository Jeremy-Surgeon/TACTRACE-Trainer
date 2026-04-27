# Changelog

All notable changes to the TACTRACE Trainer are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
TACTRACE follows a versioned hardware revision scheme: V1.0 → V1.4 → V2.x.

---

## [V1.4] — 2026-04-14 — Rotary Selector Contact Protection Revision

### Added
- 100 nF ceramic capacitor connected from TP3 node to ground — for switching transient suppression during selector transitions.
- 100 Ω resistor on the **Position 4 (Short to Power)** path — for current limiting through the rotary contact during the Pos 4 transition.
- V1.4 simplified schematic (KiCad export).
- V1.4 lid-engraving art (panel quick-reference card with test point flow and system flow diagram).

### Changed
- Schematic annotation updated to reflect the V1.4 contact-protection components.
- Rotary selector standardized as **1P4T rotary selector switch** in all project documentation.

### Notes
- V1.4 contact-protection components reduce, but do not eliminate, switching transients on the rotary contacts. Quantitative validation under measured load is pending — flagged in the README as **"Needs peer review."**
- TACTRACE remains a bench-top trainer only; **no aircraft-airworthiness certification is claimed or implied**.

---

## [V1.4 Week 2 — Revision Pass] — 2026-05-01 — PII Masking, Quickstart Procedure, BOM Correction

### Added
- Two additional avionics-maintainer responses to the initial peer-feedback round, raising the sample to **n = 5** (two 3-Level Apprentices, two 5-Level Journeymen, one 7-Level Craftsman).

### Changed
- **`docs/TACTRACE_User_Feedback_Questionnaire.csv`** — surveyor identifying information masked. Names removed (responses listed as R1-R5), rank column removed, timestamps truncated to date only, AFSC / Career Field normalized to "Avionics" for all reviewers.
- **`docs/Peer_Feedback_Summary.md`** — updated to *n* = 5; respondent mix corrected to all-Avionics; reviewer headline ratings refreshed.
- **`docs/Quickstart.md`** — diagnostic procedure rewritten to make TP4 (GND) the explicit voltmeter reference, drop the implicit "voltage flows linearly down the chain" framing, and emphasize **comparison-based** troubleshooting. Added the V1.4 teaching note that **TP3 may remain energized in Pos 4 with the main switch off**.
- **`hardware/BOM.csv`** — perfboard specification confirmed at **2 cm x 8 cm** (was "2cm x 8cm assumed"); the matching Notes & Validation entry for perfboard dimensions is removed since it's no longer pending.
- **`hardware/BOM.pdf`** — regenerated from the corrected CSV.
- **`README.md`** — Validation & Initial Peer Feedback section refreshed to *n* = 5 with corrected respondent mix; deliverables table updated.

---

## [V1.4 Week 2] — 2026-04-29 — Hardware & Documentation Publication

### Added
- **Detailed V1.4 schematic** ([`hardware/schematics/v1_4_schematic_detailed.pdf`](hardware/schematics/v1_4_schematic_detailed.pdf)) — drawn at the component level with the 100 nF cap, 100 Ω resistor, 1P4T rotary positions (POS1 NORMAL / POS2 OPEN / POS3 SHORT GND / POS4 SHORT PWR), and TP1-TP4 banana-jack test points individually labeled.
- **Simplified V1.4 schematic** ([`hardware/schematics/v1_4_schematic_simplified.pdf`](hardware/schematics/v1_4_schematic_simplified.pdf)) — block-level orientation view.
- **V1.4 KiCad source** ([`hardware/kicad/`](hardware/kicad/)) — `.kicad_pro` plus the V1.4 simple and full schematic sheets.
- **Bill of materials**, machine- and human-readable: [`hardware/BOM.csv`](hardware/BOM.csv) and [`hardware/BOM.pdf`](hardware/BOM.pdf). Includes V1.4 line items (100 nF cap, 100 Ω resistor, lid engraving), V2 candidate parts on a separate sheet, and a Notes & Validation Items table.
- **V1.4 Quickstart** ([`docs/Quickstart.md`](docs/Quickstart.md)) — one-page reference for a maintainer who has never seen the device, including a teaching note on why TP3 still energizes in Pos 4 with the main switch off.
- **V1 Training Guide PDF** carried over as the interim training reference ([`docs/TACTRACE_V1_Training_Guide.pdf`](docs/TACTRACE_V1_Training_Guide.pdf)). The V1.4-revised guide that maps the V1 three-test-point set to the V1.4 four-test-point set is in progress.
- **User-feedback questionnaire** ([`docs/TACTRACE_User_Feedback_Questionnaire.csv`](docs/TACTRACE_User_Feedback_Questionnaire.csv)) — survey instrument for collecting trainee feedback.
- **Initial peer-feedback summary** ([`docs/Peer_Feedback_Summary.md`](docs/Peer_Feedback_Summary.md)) — five responses from avionics maintainers (two 3-Level Apprentice, two 5-Level Journeyman, one 7-Level Craftsman); preliminary, not a validation study. Surveyor identifying information masked in the underlying questionnaire CSV.
- README **Hardware & Documentation Deliverables** table, **Validation & Initial Peer Feedback** section, and **Enclosure Status** section.

### Changed
- README now embeds the **detailed** V1.4 schematic inline, replacing the simplified topology image as the canonical schematic figure.
- Hardware folder structure populated to match the layout described in [`hardware/README.md`](hardware/README.md): `kicad/`, `schematics/`, `BOM.csv`, `BOM.pdf`.
- The `archive/SCHEMATIC_V1_4_REGENERATION.md` regeneration TODO is now superseded for the inline image (resolved by `images/v1_4_schematic_detailed.png`); reference designators on V1.4 components remain pending — see the file itself.

### Deferred
- **Enclosure CAD** is intentionally deferred. The project is transitioning from FreeCAD to SolidWorks; the SolidWorks license is pending. The `hardware/enclosure/` folder is reserved and will be populated in a later revision.
- A full V1.4-revised training guide remains in progress. The V1 PDF is shipped as interim, and the V1.4 quickstart bridges the gap.

### Notes
- Initial peer feedback (n=3) indicates the trainer was usable and the test-point layout was clear to the reviewers. It does **not** establish training effectiveness across a representative cohort.
- "Resister" → "Resistor" typo corrected in the schematic source. Post-release housekeeping (reference designators, peer-review confirmation of the 100 Ω routing, component-rating confirmation) is tracked in [`archive/SCHEMATIC_V1_4_REGENERATION.md`](archive/SCHEMATIC_V1_4_REGENERATION.md).

---

## [V1.3] — 2026-03 — Test Point Architecture Refinement

### Changed
- Relocated TP1 to read protected input power (post-breaker, pre-switch).
- Separated circuit protection, control, and fault-injection stages into distinct measurable nodes (TP1 / TP2 / TP3 / TP4).

### Improved
- Diagnostic clarity for power distribution faults — trainees can now isolate breaker, switch, and selector failures independently.

---

## [V1.2] — Aircraft-Realism Pass

### Changed
- Replaced automotive fuse with aircraft-style 5 A pull-type circuit breaker.
- Transitioned from male banana plugs to panel-mounted female banana jacks.

### Improved
- Safety, standard-test-lead compatibility, and instructional realism.

---

## [V1.1] — Enclosure Integration

### Added
- Pelican 1120 enclosure with structured control panel layout.

### Improved
- Durability and portability for transport between training sites.

---

## [V1.0] — 2026-02 — Functional Validation

### Added
- Initial circuit concept and four-position rotary fault selector (Normal / Open / Short-to-Ground / Short-to-Power).
- 24 V DC supply, fuse, power switch, LED + 1 kΩ resistor load, banana-jack test points.
- Initial bench validation of all four fault conditions.

---

## Conventions

- Hardware revisions are tagged in this repository as `v1.0`, `v1.1`, `v1.2`, `v1.3`, `v1.4`, and so on.
- Each entry uses the **Added / Changed / Removed / Improved / Notes** sub-headings from Keep a Changelog where they apply.
- Claims that have not yet been validated by measured testing or independent peer review are marked **"Needs peer review"** in the README.
