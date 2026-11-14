# Six-Channel Soma Specification

**Status:** Proposed functional interface.

Preserve six independently functioning soma processing channels in every standard N1 neuron. They must not collapse into one unobservable amplifier path.

| Channel | Role | Candidate analogue behaviour |
|---|---|---|
| S1 Fast | Rapid integration | Short-time-constant current/voltage path |
| S2 Slow | Temporal integration | Longer RC integration |
| S3 Context | Contextual/top-down modulation | Weighted context input |
| S4 Integrator | Evidence and membrane accumulation | Summing/integrating path |
| S5 Burst | Burst-related response | Pulse-history or threshold-adaptation path |
| S6 Gating | Input admission and excitability | Voltage-controlled gain/conductance |

For each channel document input range/common-mode, input impedance/isolation, gain and transfer function, time constant/bandwidth, saturation/recovery, modulation dependencies, output range/impedance, test point and calibration.

The soma combiner must expose each channel's contribution. A weighted current-summing network is a candidate; weights must be configurable and bounded. Demonstrate that changing one channel does not silently remove another channel's behaviour.
