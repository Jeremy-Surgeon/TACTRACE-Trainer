# Documentation

Training materials, instructor reference, and validation artifacts for the TACTRACE Trainer.

## Contents

- **[`Quickstart.md`](Quickstart.md)** — One-page V1.4 quickstart for a maintainer who has never seen the device. Includes setup procedure, fault-selector position table, test-point map, the recommended diagnostic procedure, and a list of "things that surprise first-time users" derived from initial peer feedback.
- **[`TACTRACE_V1_Training_Guide.pdf`](TACTRACE_V1_Training_Guide.pdf)** — V1 Training Guide: full 13-page document with trainee worksheet (Part I), instructor reference (Part II), expected-voltage and expected-resistance tables, and an instructor evaluation rubric. **Interim**: this PDF documents the V1 three-test-point set (TP1, TP2, TP3, GND); the V1.4 four-test-point set (TP1, TP2, TP3, TP4) is described in the V1.4 Quickstart and project README. A V1.4-revised full guide is in progress.
- **[`TACTRACE_User_Feedback_Questionnaire.csv`](TACTRACE_User_Feedback_Questionnaire.csv)** — Five anonymized responses from the initial peer-feedback round. Surveyor identifying information (names, ranks) is masked; reviewers are listed under R1-R5. Suitable for direct reuse as a Google Forms / Excel-import template if the original schema is restored.
- **[`Peer_Feedback_Summary.md`](Peer_Feedback_Summary.md)** — Initial peer-feedback round (n = 5) from avionics maintainers: two 3-Level Apprentices, two 5-Level Journeymen, one 7-Level Craftsman. Reports headline ratings, common improvement themes (selector-knob labeling, request for a written manual, V2 cannon-plug realism), and an explicit list of what this round does **not** establish.

## Planned (Next Revision)

- **`TACTRACE_V1.4_Training_Guide.pdf`** — V1.4-revised full training guide, mapping the V1 three-test-point set (TP1-TP3 + GND) to the V1.4 four-test-point set (TP1-TP4), and updating the expected-readings tables for the new TP layout.
- **`Trainee_Worksheet.pdf`** — Standalone trainee worksheet pulled out of the full guide for single-page printing.
- **`Instructor_Reference.pdf`** — Instructor-side reference (setup procedure, fault-mode tables, evaluation rubric) split out of the full guide for desk-reference use.
- **`V2_design_brief.md`** — Formal V2 design brief: requirements, architecture options, open questions, risk register.

## Conventions

- Published documents are PDF or Markdown. Source files (Pages, Word) are kept locally; only exported / Markdown documents are committed.
- Documentation revisions are tracked in [`../CHANGELOG.md`](../CHANGELOG.md) when they are released alongside a hardware revision.
- Claims that have not yet been validated by measured testing or independent peer review are marked **"Needs peer review"** in the README and the source files.
- Peer-feedback summaries report only what reviewers stated; broader claims about training effectiveness, learning gains, or transfer to flight-line tasks are explicitly **not** asserted unless backed by a designed study with adequate sample size.
