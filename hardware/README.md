# Hardware

Schematic, PCB, mechanical, and bill-of-materials files for the TACTRACE Trainer.

## Planned Contents

- **`kicad/`** — KiCad project (`*.kicad_pro`, `*.kicad_sch`, `*.kicad_pcb`) for the V1.x electrical design.
- **`schematics/`** — Exported schematics in PDF, PNG, and SVG for the V1.4 simplified and detailed forms.
- **`enclosure/`** — FreeCAD source (`*.FCStd`) and exported PDFs for the Pelican 1120 panel layout and lid engraving.
- **`BOM.csv`** — Bill of materials: component, value, package, vendor, vendor part number, quantity, notes.
- **`panel/`** — Panel-engraving art (lid engraving, label artwork).

## Conventions

- KiCad backups (`*-backups/`, `_autosave-*`) and FreeCAD backups (`*.FCBak`) are excluded via [`../.gitignore`](../.gitignore).
- Each export PDF is regenerated from the KiCad/FreeCAD source whenever the source changes.
- Hardware revisions are tagged in [`../CHANGELOG.md`](../CHANGELOG.md).

## V1.4 Highlights

- 100 nF ceramic capacitor connected from TP3 node to ground for switching transient suppression during selector transitions.
- 100 Ω resistor on the Position 4 (Short to Power) path for current limiting through the rotary contact.
- Updated lid engraving with TP1 → TP2 → TP3 → TP4 flow reference.

The simplified V1.4 schematic is reproduced inline in the [project README](../README.md). The detailed V1.4 schematic — drawing each contact-protection component in its precise location — will be published here in the next revision.
