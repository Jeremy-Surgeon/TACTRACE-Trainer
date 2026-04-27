# V1.4 Schematic — Regeneration Required

**Status:** Open — flagged 2026-04-27
**Owner:** Jeremy Surgeon
**Target milestone:** Week 2 (`hardware/` publication)

## Issue

The current `images/v1_4_schematic.png` shipped with the V1.4 parity README is the **simplified V1.0/V1.2 topology** — it does **not** individually depict the V1.4-specific contact-protection components:

- 100 nF ceramic capacitor from the TP3 node to ground (transient suppression during selector transitions)
- 100 Ω resistor on the **Position 4 (Short to Power)** path (current limiting through the rotary contact)

The README acknowledges this gap explicitly with a "Needs peer review" caveat (see the V1.4 Schematic section), so the public repo is internally consistent — but the simplified drawing is interim, not the final V1.4 deliverable.

## Action required

Regenerate `images/v1_4_schematic.png` from the **V1.4 KiCad source** showing each contact-protection component in its precise location:

1. Open the V1.4 KiCad project (Week 2 deliverable in `hardware/`).
2. Annotate the 100 nF cap at TP3-to-GND, with reference designator and value visible.
3. Annotate the 100 Ω resistor on the Pos 4 path of the 1P4T rotary, with reference designator and value visible.
4. Export a cropped PNG suitable for inline README embedding (target: ≤ 100 KB, transparent or white background, ≥ 1200 px wide).
5. Replace `images/v1_4_schematic.png`. Move the existing simplified PNG to `archive/v1_4_schematic_simplified.png` for traceability.
6. Update the caveat in `README.md` to remove the "not individually drawn" caveat once the detailed schematic is the embedded image.

## Out of scope for this fix

- Full A4 KiCad sheet export with title block and test-point reference table — keep that as a separate `hardware/v1_4_schematic_full_sheet.pdf` (or `.png`) deliverable; the README inline image should remain the cropped, focused view.
- Bill of materials, PCB layout, FreeCAD enclosure model — tracked separately in the Week 2 plan (see `DEPLOY_NOTES.md`).

## Verification

After regeneration, the V1.4 schematic image must:

- [ ] Render the 100 nF capacitor as a discrete component with refdes and value.
- [ ] Render the 100 Ω resistor as a discrete component with refdes and value, on the Pos 4 path.
- [ ] Match the textual description in `README.md` lines 51–55 and the Key Engineering Decisions section.
- [ ] Pass peer review under measured load before any "validated" claim is made in README copy.

Until all four boxes check, the V1.4 hardware claim in this repo remains **"Needs peer review."**
