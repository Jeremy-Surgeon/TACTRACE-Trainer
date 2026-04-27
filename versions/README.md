# Versions

Per-version archives of the TACTRACE Trainer source files.

## Purpose

Each major hardware revision (V1.0, V1.1, V1.2, V1.3, V1.4, …) is archived in its own subfolder so that the exact state of the project at each revision is reproducible from this repository.

The `main` branch always reflects the latest revision; the per-version archives here exist for historical reference.

## Planned Contents

```
versions/
├── v1.0/   ← initial functional validation (Digital simulator .dig files, prototype notes)
├── v1.1/   ← Pelican 1120 enclosure integration
├── v1.2/   ← aircraft-style breaker, female banana jacks
├── v1.3/   ← TP1 relocation post-breaker (4-test-point architecture)
└── v1.4/   ← rotary selector contact protection (100 nF from TP3 to GND, 100 Ω on Pos 4 path)
```

Each version subfolder contains the schematic, BOM, panel art, and any documentation that was current at the time of that revision.

## Conventions

- A new subfolder is added when a hardware revision is tagged.
- Existing version folders are not edited after their tag is cut. Corrections and clarifications are made on `main`.
- Per-version changes are summarized in [`../CHANGELOG.md`](../CHANGELOG.md).
