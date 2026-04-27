# V1.4 Schematic — Outstanding Items

**Status:** Mostly resolved as of 2026-04-29.
**Owner:** Jeremy Surgeon

## Resolved in the V1.4 release

- **Detailed V1.4 schematic published** at [`../hardware/schematics/v1_4_schematic_detailed.pdf`](../hardware/schematics/v1_4_schematic_detailed.pdf), with KiCad source at [`../hardware/kicad/`](../hardware/kicad/) and a PNG render at [`../images/v1_4_schematic_detailed.png`](../images/v1_4_schematic_detailed.png) (embedded in the project README).
- **Typo corrected** in the schematic source: "Resister" → "Resistor" on both the 1 kΩ load resistor and the 100 Ω current-limit resistor.
- **All V1.4 components drawn explicitly:** CB (5 A), TP1, SW1 (SW_SPST), TP2, the 100 Ω resistor on the Pos 4 path, the 1P4T rotary fault selector with all four positions labeled (POS1 NORMAL, POS2 OPEN, POS3 SHORT GND, POS4 SHORT PWR), TP3, the 1 kΩ load resistor, the LED (D1), the 100 nF capacitor across the load, and TP4 / GND.

## Items still open (post-V1.4 housekeeping)

These do **not** block the V1.4 release:

- [ ] **Reference designators.** V1.4 components are labeled by value only. Standard refdes (R1, R2, C1, …) should be added in the next schematic revision.
- [ ] **Peer-review confirmation of the 100 Ω routing.** The schematic shows the 100 Ω feeding rotary Pos 4 from the **post-CB rail** (bypassing SW1). This is consistent with the V1.4 teaching narrative documented in [`../docs/Quickstart.md`](../docs/Quickstart.md): TP3 still energizes in Pos 4 with the main switch off — that is the diagnostic signature. Open item is an independent peer-review confirmation that this is the design-intended path.
- [ ] **Component ratings.** The 100 Ω wattage rating and the 100 nF tolerance + voltage rating are tracked in [`../hardware/BOM.csv`](../hardware/BOM.csv) under "Notes & Validation Items" and should be confirmed against the installed parts.

Until each box checks, the V1.4 contact-protection components remain **"Needs peer review"** in the README under quantitative validation.
