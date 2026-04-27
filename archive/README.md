# archive/

This folder holds **internal traceability artifacts** for the TACTRACE Trainer project — superseded drafts, regeneration TODOs, and historical exports that should not be deleted but also do not belong in `images/`, `hardware/`, or `docs/`.

It is published with the repo so that reviewers can see the full V1.4 paper trail, including known gaps, without those gaps polluting the user-facing folders.

## Current contents

- [`SCHEMATIC_V1_4_REGENERATION.md`](SCHEMATIC_V1_4_REGENERATION.md) — flags `images/v1_4_schematic.png` as the simplified V1.0/V1.2 topology pending Week 2 regeneration from the V1.4 KiCad source. Includes regeneration steps and verification checklist.

## What does not belong here

- Photos, schematics, or panel art that are the current canonical V1.4 deliverables — those go in `images/`.
- KiCad / FreeCAD / BOM source files — those go in `hardware/`.
- Training documents, instructor materials — those go in `docs/`.
- Bench validation logs, peer review notes — those go in `logs/`.
- Per-version source archives — those go in `versions/`.

If a file in `archive/` has been superseded **and** is no longer needed for traceability (e.g., a draft replaced by a peer-reviewed final), record the supersession in this README and remove the file in a documented commit.
