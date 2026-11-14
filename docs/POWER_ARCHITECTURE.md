# Power, Grounding and Electrical Safety

**Status:** Preliminary requirements; not a certified power design.

## Separate domains

Positive analogue rail(s), negative analogue rail if needed, sensor excitation/supply, motor power and an independent safety/power-monitoring domain. Choose rails only after N1 components and signal ranges are selected.

## Noise and grounding

- Keep high-current motor returns away from sensitive analogue returns.
- Define deliberate grounding/reference topology.
- Decouple each IC locally.
- Filter motor transients and consider physical separation.
- Use differential signalling on vulnerable inter-board paths.
- Measure ripple, ground offsets and motor-induced noise.

## Battery and protection

Use a suitable BMS, fuse, overcurrent and undervoltage protection, thermal monitoring and correctly rated wiring/connectors. Select battery chemistry, cell configuration and charger as one engineered system. Never charge unattended during prototype testing.

## Bench-first procedure

1. Use current-limited laboratory supplies.
2. Verify polarity and rails before inserting sensitive ICs.
3. Power analogue boards without motors.
4. Test thermal rise and short-circuit response.
5. Add sensor loads.
6. Add motor drivers with wheels raised.
7. Verify emergency stop and fault behaviour.
8. Only then consider battery operation.

This document does not replace datasheets, battery safety procedures or competent electrical review.
