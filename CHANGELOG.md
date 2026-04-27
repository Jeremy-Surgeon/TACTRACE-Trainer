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
- The simplified V1.4 schematic shows the topology at a block level; the V1.4 contact-protection components (100 nF from TP3 to GND, 100 Ω on the Pos 4 path) are not drawn individually in that view. The detailed V1.4 schematic will be published in `hardware/` (Week 2).
- V1.4 contact-protection components reduce, but do not eliminate, switching transients on the rotary contacts. Quantitative validation under measured load is pending — flagged in the README as **"Needs peer review."**
- Precise schematic placement of the 100 Ω on the Pos 4 path (source-side vs. contact-side of the rotary) will be confirmed in the Week 2 detailed-schematic publication.
- TACTRACE remains a bench-top trainer only; **no aircraft-airworthiness certification is claimed or implied**.

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
