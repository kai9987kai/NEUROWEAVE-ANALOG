# Custom Physical Neuron Architecture

**Status:** Proposed specification; N1 circuit not yet validated.

## Objective

Implement a modular physical neuron retaining four dendritic compartments, six independent soma channels, continuous membrane state, adaptive threshold, refractory behaviour, calcium-like dynamics, axonal distribution and plasticity interfaces.

## Functional block diagram

```text
Dendrite P ─┐
Dendrite D ─┤
Dendrite A ─┼─> Six-channel soma bank ─> Membrane/threshold ─> Spike generator
Dendrite B ─┘              ↑                    ↑                    │
                           │                    │                    v
                   Modulatory inputs     Calcium/adaptation    Axon branches
                           ↑                                         │
                    Receptor profiles                    Synaptic terminals
                           ↑                                         │
                    Local state buses <──── feedback / eligibility ──┘
```

## Four dendritic compartments

Each compartment requires a separate state node, input impedance, effective leak, configurable synaptic input and measurable output.

| ID | Label | Intended role | Verification |
|---|---|---|---|
| D1 | Proximal | Faster local integration | Step response and decay |
| D2 | Distal | Slower/delayed integration | Time constant and isolation |
| D3 | Apical | Context/modulatory input | Modulator sensitivity |
| D4 | Basal | Sensory and E/I input | Excitatory/inhibitory response |

Provisional dynamics:

[
C_irac{dV_i}{dt}=sum_j I_{ij}-rac{V_i-V_{rest,i}}{R_i}
]

A conductance synapse may be represented as (I_{ij}=g_{ij}(E_{ij}-V_i)). Component values and voltage ranges must be derived from chosen rails, circuit topology and desired time constants.

## Six soma channels

| ID | Channel | Intended function |
|---|---|---|
| S1 | Fast | Rapid excitatory/inhibitory integration |
| S2 | Slow | Longer temporal integration |
| S3 | Context | Contextual/top-down influence |
| S4 | Integrator | Evidence accumulation/membrane coupling |
| S5 | Burst | Burst-related dynamics |
| S6 | Gating | Excitability/input-admission modulation |

Each requires defined input, transfer function, time constant, gain/range, output impedance, modulation inputs and test point. Soma combining must retain observable channel contributions and bounded configurable weights; avoid undocumented summation or uncontrolled positive feedback.

## Membrane, threshold and spike

Candidate relation:

[
C_mrac{dV_m}{dt}=I_{dendrites}+I_{recurrent}-I_{leak}-I_{adapt}
]

A threshold stage produces a bounded pulse; a refractory circuit suppresses retriggering and an adaptive threshold changes subsequent excitability. Candidate blocks: op-amp integrators, transconductance stages, comparators, transistor pulse drivers and RC timing networks. Check supply range, headroom, offset, bias current, bandwidth, noise, stability and temperature.

## Calcium-like state and adaptation

Use bounded leaky integrators for slow state variables. They may influence threshold, burst response or plasticity. Specify decay, reset and saturation. Do not equate voltage with real intracellular calcium.

## Axonal output

Provide primary output and separately configurable branches. Specify pulse amplitude, polarity, duration, source impedance, fan-out, load and isolation. Terminal stages convert pulses into the receiving synapse's current/conductance interface.

## Modulation and plasticity interfaces

Expose separate modulation signals and plasticity/eligibility control. Receptor-inspired responses are analogue transfer functions, not biological receptors.

## Calibration and observability

Required probe points: four dendritic states, six soma outputs, membrane, threshold control, spike, refractory state, calcium-like state, adaptation, axon branches and synaptic conductance/update state. Document offset, gain, time constants, threshold, pulse shape, component tolerance and temperature.

## N1 acceptance criteria

1. Each dendritic compartment responds independently.
2. Four compartments have distinguishable time responses.
3. All six soma channels are independently injectable and observable.
4. Channel contributions to membrane integration are reproducible.
5. Threshold crossing produces a bounded repeatable pulse.
6. Refractory behaviour suppresses retriggering as specified.
7. Calcium/adaptation traces show measured decay and influence excitability.
8. Axonal branches drive defined loads without destabilising the soma.
9. Supply, temperature and noise envelopes are documented.
10. Schematic, BOM, PCB sources and test evidence are archived.
