# N1 — Complete Custom Analogue Neuron Module

**Status:** Design target; no validated schematic or PCB yet.

Required blocks:
1. Four independent dendritic compartments.
2. Six independent soma channels.
3. Measurable soma combining network.
4. Membrane integrator.
5. Adaptive threshold.
6. Spike generator and refractory circuit.
7. Calcium-like slow-state circuit.
8. Activity adaptation.
9. Primary axon output and branches.
10. Synaptic input/terminal interfaces.
11. Neuromodulation inputs.
12. Plasticity/eligibility interface.
13. Supply conditioning, decoupling and test points.

Required deliverables: block and complete electrical schematics; component BOM with part numbers/alternatives; signal/rail definitions and pinout; editable PCB and manufacturing outputs; assembly/calibration procedure; circuit simulations; bench protocol/raw evidence; revision history/limitations.

Do not release a simplified N1 omitting dendrites, soma channels or internal states. If the complete design is too large, use connected sub-boards while preserving a complete N1 as the specified unit.

Component selection remains open until rails, ranges, gains and time constants are defined. Candidate categories: low-noise op-amps, comparators, transconductance stages, analogue switches, MOSFETs/BJTs, precision resistors, stable capacitors, connectors and protection. A TLV9064-class quad op-amp may be evaluated for suitable low-voltage sections; it is not a universal selection. Check the current datasheet and circuit requirements.
