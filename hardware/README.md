# Hardware

Schematic, KiCad source, and bill-of-materials files for the TACTRACE Trainer.

## Contents

- **[`kicad/`](kicad/)** — KiCad project (`*.kicad_pro`, `*.kicad_sch`) for the V1.4 electrical design.
  - `TacTrace_V1.kicad_pro` — KiCad project file.
  - `TacTrace_V1_4_Full.kicad_sch` — V1.4 detailed schematic source (drawn at the component level).
  - `TacTrace_V1_4_Simple.kicad_sch` — V1.4 simplified topology source (block-level orientation view).
- **[`schematics/`](schematics/)** — PDF exports.
  - `v1_4_schematic_detailed.pdf` — V1.4 detailed schematic with the 100 nF cap, 100 Ω resistor, 1P4T rotary positions, and TP1-TP4 banana jacks individually labeled.
  - `v1_4_schematic_simplified.pdf` — V1.4 simplified block-level topology.
- **[`BOM.csv`](BOM.csv)** — Bill of materials, machine-readable. 15 installed line items + V2 candidate parts + Notes & Validation Items section.
- **[`BOM.pdf`](BOM.pdf)** — Bill of materials, human-readable (landscape, three-section layout matching the CSV).

## Planned (Future Revision)

- **`enclosure/`** — SolidWorks source (`*.SLDPRT`, `*.SLDASM`) and exported PDFs for the Pelican 1120 panel layout and lid engraving. **Deferred** while transitioning from FreeCAD to SolidWorks; license pending. The current enclosure is documented through panel-engraving art and the photographic record in [`../images/`](../images/).
- **`panel/`** — Panel-engraving art (lid engraving, label artwork), separated from photographs.
- **PCB layout (`*.kicad_pcb`)** — V1.4 is perfboard; a custom PCB is a V2 candidate.

## Conventions

- KiCad backups (`*-backups/`, `_autosave-*`) and FreeCAD backups (`*.FCBak`) are excluded via [`../.gitignore`](../.gitignore).
- Each export PDF is regenerated from the KiCad source whenever the source changes.
- Hardware revisions are tagged in [`../CHANGELOG.md`](../CHANGELOG.md).

## V1.4 Highlights

- **100 nF ceramic capacitor** from the TP3 node to ground — switching-transient suppression during selector transitions.
- **100 Ω resistor** on the Pos 4 (Short to Power) path — current limiting through the rotary contact. The schematic shows this resistor fed from the post-breaker rail; this is intentional, and the V1.4 quickstart documents the resulting diagnostic signature (TP3 still energizes in Pos 4 even with the main power switch off).
- **Updated lid engraving** with the TP1 → TP2 → TP3 → TP4 flow reference.

## Items Pending Verification

Tracked in [`../archive/SCHEMATIC_V1_4_REGENERATION.md`](../archive/SCHEMATIC_V1_4_REGENERATION.md):

- Reference designators (R1, R2, C1, …) for V1.4 components — currently labeled by value only.
- Independent peer-review confirmation that the 100 Ω placement (post-CB → rotary Pos 4, bypassing SW1) is the design-intended path. The schematic is consistent with the V1.4 teaching narrative; this is a confirmation step, not a known defect.
- 100 Ω wattage rating; 100 nF tolerance and voltage rating — both flagged in [`BOM.csv`](BOM.csv) Notes & Validation Items.
