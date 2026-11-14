# Analogue Motor Planning and Execution

**Status:** Proposed.

Motor planning populations generate directional/velocity-related analogue signals. Motor execution circuits condition and limit commands. Motor drivers supply actuator current. Encoder, current and inertial feedback return to proprioceptive populations. Independent hardware safety may interrupt motor power.

For a differential-drive abstraction:

[
V_L=V_{forward}+V_{turn},quad V_R=V_{forward}-V_{turn}
]

Real drivers require calibrated ranges, deadbands, slew limits, current limits and safe defaults.

Initial body: low-speed six-wheel rover with low centre of gravity, guarded wheels, bumper, accessible emergency stop and modular enclosure.

Safety requirements:
- Emergency stop physically interrupts motor enable/power.
- Motor current is limited.
- Battery protection is independent.
- Actuator thermal limits are observed.
- Loss of sensory/command signal leads to a safe state.
- Test first with wheels raised, then tethered/low-speed in a clear enclosure.
- No autonomous testing near people, roads, stairs or animals until controlled tests pass.

Measure command-to-speed, steering response, deadband, braking/coast, feedback stability, current, temperature and stopping distance.
