# Logs

Bench-validation records, peer-review notes, and test logs for the TACTRACE Trainer.

## Planned Contents

- **`YYYY-MM_v1.4_bench_validation.md`** — Measured TP1–TP4 voltages and resistances at each fault position, with the rotary in each of positions 1–4, with the trainer powered (24 V) and unpowered.
- **`YYYY-MM_v1.4_arc_validation.md`** — Quantitative validation of the V1.4 contact-protection components (100 nF from TP3 to GND, 100 Ω on Pos 4 path) — switching-transient capture and analysis. *Pending.*
- **`YYYY-MM_peer_review_<reviewer>.md`** — Peer-review notes from contributors who have inspected or used the trainer.

## Conventions

- One file per validation event. Filename: `YYYY-MM_<topic>.md`.
- Each log records: hardware revision, supply voltage, instruments used, raw measurements, and an interpretation paragraph.
- Anything claimed in the README that has not yet been validated by a log entry is flagged in the README as **"Needs peer review."**

## Status

V1.4 has been bench-built and demonstrated; a formal validation log is pending and is the first deliverable for the V1.4 publication sprint Week 4.
