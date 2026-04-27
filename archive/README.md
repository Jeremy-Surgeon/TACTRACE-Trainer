# archive/

This folder holds **internal traceability artifacts** for the TACTRACE Trainer project — superseded drafts, regeneration TODOs, and historical exports that should not be deleted but also do not belong in `images/`, `hardware/`, or `docs/`.

It is published with the repo so that reviewers can see the full V1.4 paper trail, including known gaps, without those gaps polluting the user-facing folders.

## Current contents

- [`SCHEMATIC_V1_4_REGENERATION.md`](SCHEMATIC_V1_4_REGENERATION.md) — schematic open-item tracker. The detailed V1.4 schematic is now published at [`../hardware/schematics/v1_4_schematic_detailed.pdf`](../hardware/schematics/v1_4_schematic_detailed.pdf) and embedded in the project README. The remaining items are a "Resister" → "Resistor" typo correction, reference-designator additions (R1, C1, …), and peer-review confirmation of the 100 Ω routing intent.

## What does not belong here

- Photos, schematics, or panel art that are the current canonical V1.4 deliverables — those go in `images/`.
- KiCad / FreeCAD / BOM source files — those go in `hardware/`.
- Training documents, instructor materials — those go in `docs/`.
- Bench validation logs, peer review notes — those go in `logs/`.
- Per-version source archives — those go in `versions/`.

If a file in `archive/` has been superseded **and** is no longer needed for traceability (e.g., a draft replaced by a peer-reviewed final), record the supersession in this README and remove the file in a documented commit.
