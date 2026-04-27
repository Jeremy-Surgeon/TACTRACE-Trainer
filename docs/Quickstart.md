# TACTRACE Trainer — V1.4 Quickstart

A one-page reference for a maintainer who has never seen the device. For the full training procedure (trainee worksheet + instructor reference + evaluation rubric), see the V1 Training Guide PDF in this folder until the V1.4-revised guide is published.

> **Document status:** V1.4 quickstart, draft. The full V1.4 Training Guide is in revision (V1 source PDF retained as `TACTRACE_V1_Training_Guide.pdf`). Mapping the V1 test-point set (TP1-TP3 + GND) to the V1.4 four-test-point set (TP1-TP4) is the core change between the two revisions.

---

## Equipment

- TACTRACE Trainer (V1.4)
- 24 V DC 3 A power adapter (5.5 x 2.1 mm barrel) — included
- Digital multimeter with standard test leads

## What you have

A 24 V DC bench-top trainer with a 1P4T rotary fault selector and four panel-mount banana-jack test points. The lid carries an engraved quick-reference card showing the test-point order, the system flow, and the troubleshooting reminder that **continuity may not read through the load — use voltage to verify operation.**

## Setup procedure

1. Plug the 24 V adapter into the trainer's panel-mount barrel jack.
2. Confirm the **circuit breaker (CB)** is **pushed in** (closed).
3. Set the **rotary fault selector** to the position the instructor has assigned (1, 2, 3, or 4).
4. Turn the **power switch ON** to begin the diagnostic exercise.

## Fault selector positions

| Position | Fault Condition | What it does |
|---------:|-----------------|---------------|
| 1        | Normal           | Healthy circuit — power flows to the load through the rotary |
| 2        | Open Circuit     | Path between the selector and the load is broken |
| 3        | Short to Ground  | The post-selector node (TP3) is shorted to ground return |
| 4        | Short to Power   | TP3 is fed from the supply through a 100 Ω current-limit on this path |

> **V1.4 teaching note (Pos 4):** the 100 Ω current-limit feeds Pos 4 from the post-breaker rail, so TP3 still energizes in Pos 4 even with the **main power switch OFF**. That is the diagnostic signature that distinguishes Short-to-Power from the other faults.

## Test points

| Label | Location                                       | Function                                                    |
|-------|------------------------------------------------|-------------------------------------------------------------|
| TP1   | After circuit breaker, before power switch     | Verifies protected input power                               |
| TP2   | After power switch, before fault selector      | Verifies power entering the fault selector                   |
| TP3   | After fault selector, before load              | Displays the selected fault condition                        |
| TP4   | Load return / ground reference                 | System ground reference                                      |

## Diagnostic procedure

Voltage measurements are taken **with the black probe on TP4 (GND)** and the red probe stepped through TP1, TP2, and TP3. Don't assume voltage propagates linearly down the chain — read each test point independently and **compare the readings** to identify which node behaves anomalously for the active fault.

1. **Reference probe at TP4 (GND).** Set the multimeter to DC volts. Keep the black probe on TP4 for every voltage reading in this procedure.
2. **Capture the four readings.** With power **ON**, read TP1, TP2, and TP3 in any order. Record each voltage. Note the LED state (on / off / dim).
3. **Compare, don't assume.** Identify the test point where the reading diverges from the expected value and the test point where it agrees. The pair tells you where the fault is — not the order.
4. **Distinguish Pos 4 from the rest.** **TP3 may remain energized in Position 4 even with the main power switch OFF**, because the 100 Ω current-limit feeds Pos 4 from the post-breaker rail. If TP3 still reads near +24 V with the switch off, the rotary is on Pos 4 (Short to Power).
5. **Power OFF for any continuity / resistance check.** Pull the breaker for resistance work. **Do not perform resistance tests with the supply energized.**
6. **Record and document.** Note the fault you identified and your reasoning (which TP-pair was the deciding evidence). The full per-fault expected-reading table is in the V1 Training Guide PDF (Part II — Instructor Reference).

## Things that surprise first-time users (from peer feedback)

- The selector knob does not name the faults at the panel — refer to the lid-engraved reference card or this Quickstart.
- A pulled circuit breaker can read **0 V** at TP1, or read very low (≤ 0.1 V) due to multimeter noise — both indicate "no protected input power."
- Touching probe tips with bare fingers can shift readings; keep fingers off the metal.
- The probe leads themselves can complete the circuit and light the LED if you bridge the load — a useful demonstration, but be aware of it during measurement.
- Continuity (audible) may not beep through the LED + 1 kΩ load even when the path is intact — use **voltage** to verify operation.

## Safety

- **No certification.** TACTRACE is a bench-top trainer only. It is **not** certified for use on or with airworthy aircraft.
- Resistance / continuity checks: **power OFF**, breaker pulled.
- Do not short test points together with bare probe leads while power is applied beyond what the exercise requires.
- The 5 A breaker provides primary input protection; the 100 Ω in the Pos 4 path provides current limiting through the rotary contact during Short-to-Power. Both are wear-rated, not safety-rated for high-energy faults.

---

> Where this quickstart and the V1 PDF disagree, the V1.4 hardware (this quickstart) is authoritative. Items still requiring peer review are flagged in the [project README](../README.md) and the [CHANGELOG](../CHANGELOG.md).
