# Master Architecture

**Version:** 0.1 — proposed architecture  
**System:** Pure-analogue neuromorphic mobile robot  
**Initial embodiment:** Six-wheel rover

## 1. Mission and system boundary

Translate the custom NEUROWEAVE neuron, connectome, modulatory and sensory concepts into a physical analogue nervous system. Continuous electrical states represent neuronal and synaptic state; physical circuit interactions perform processing and influence motor behaviour.

No digital processor may execute neural inference, choose actions or substitute a software network for the analogue connectome in the operational cognitive pathway. External computers may design circuits, analyse recorded data and support development. Instrumentation may observe the system but must not close a hidden behavioural-control loop.

**Inside the nervous system:** analogue sensor front ends, dendrites, six soma channels, membrane/spike dynamics, synapses, plasticity, neuromodulation, recurrent connectome, physical memory, prediction, motor planning and sensorimotor feedback.

**Outside the cognitive pathway:** development computers, PCB and circuit simulation tools, offline analysis, manual configuration fixtures, and independent emergency stop, battery protection, current limiting and thermal protection. Safety circuitry may interrupt power or constrain actuators; it does not make cognitive decisions.

## 2. Layered physical architecture

1. Transduction: optical, acoustic, tactile, inertial, proximity and proprioceptive sensors.
2. Analogue sensory front ends: amplification, filtering, envelope detection, contrast/motion channels and calibration.
3. Neuron modules: four dendritic compartments, six soma channels, membrane state, spike generation and axonal output.
4. Synaptic fabric: weighted excitatory/inhibitory conductances, local recurrent paths, routing and plasticity.
5. Modulatory fabric: shared/local state signals that change gain, threshold, learning rate or receptor-inspired response.
6. Regional connectome: sensory, spatial, associative, memory, predictive, affective and motor populations.
7. Motor substrate: analogue planning/execution, motor drivers and physical feedback.
8. Embodiment: protected power, chassis, wheels, enclosure and test points.

## 3. Neuron invariants

### Four dendritic compartments

Each compartment has a distinct local state and time constant. Provisional roles:

- **Proximal:** fast local synaptic integration.
- **Distal:** delayed or slower integration.
- **Apical:** contextual/top-down modulation.
- **Basal:** sensory and local excitatory/inhibitory integration.

These are functional engineering roles, not a claim of full biological dendrite replication.

### Six soma channels

Maintain six independently measurable channels:

1. Fast integration.
2. Slow integration.
3. Contextual modulation.
4. Evidence/membrane integration.
5. Burst-related dynamics.
6. Gating/excitability modulation.

Channel transfer functions, time constants, input/output ranges, gain and coupling must be frozen in an interface-control document before N1 schematic release. All six remain separately observable and independently testable.

### Other neuronal states

Membrane potential, adaptive firing threshold, refractory state, action-potential pulse, calcium-like slow state, activity adaptation, persistent/eligibility traces and optional predictive/context state. Use bounded stable circuits. A capacitor voltage can model a transient state but is not inherently nonvolatile memory.

Candidate membrane relation:

[
C_mrac{dV_m}{dt}=I_{dendrites}+I_{recurrent}-I_{leak}-I_{adapt}
]

A comparator-based threshold stage triggers a bounded pulse. Refractory timing suppresses retriggering; adaptation changes subsequent excitability.

## 4. Synapse and axon architecture

Synapses are physical conductance/current pathways. Excitatory and inhibitory paths are both required. Every synaptic interface must specify pulse levels, polarity, conductance range, time response, update mechanism, isolation and failure behaviour.

Axonal outputs include primary output, configurable branches, terminal drivers and documented feedback routes. Use noise-aware interconnect; differential signalling is preferred for long or interference-prone paths.

[
I_{syn}=g_{syn}(V_{pre}-E_{syn})
]

## 5. Neuromodulation

Preserve separate receptor-inspired modulation rather than collapsing everything into one scalar:

- Dopamine-like: reward/learning modulation.
- Serotonin-like: slow stability modulation.
- Noradrenaline-like: arousal/gain modulation.
- Acetylcholine-like: attention/learning modulation.
- Octopamine-like: state-dependent modulation.
- Endocannabinoid-like: local/retrograde modulation.
- GABA-like: inhibitory conductance.
- Glutamate-like: excitatory conductance.

Retain distinct response profiles inspired by D1/D2, 5-HT1A/5-HT2A, adrenergic, muscarinic, octopamine and CB1 families. These are electrical transfer-function abstractions, not biological chemicals or actual receptors.

Regional modulation buses plus local response circuits are preferred. A candidate effective-conductance relation is:

[
g_{effective}=g_{base}f(V_{mod},V_{context})
]

Define and measure (f) for each target circuit; bound ranges and include saturation/recovery.

## 6. Plasticity and physical memory

Target short-term facilitation/depression, STDP-like timing-dependent updates, modulator-gated learning, eligibility traces, homeostatic stabilisation and structural connectivity changes.

A simplified STDP target is:

[
Delta w =
egin{cases}
A_+e^{-Delta t/	au_+}, & Delta t>0\
-A_-e^{Delta t/	au_-}, & Delta t<0
end{cases}
]

where (Delta t=t_{post}-t_{pre}). Physical implementation may use pulse overlap, charge or analogue state circuits; measure the actual update curve.

Capacitors provide volatile traces only. Memristors are an R&D option, not a first-prototype dependency. Characterise device variability, retention, endurance, programming requirements, update symmetry and temperature sensitivity before use. A persistent memory mechanism remains an explicit research dependency.

## 7. Connectome regions and targets

Proposed populations: visual/sensory, auditory, somatosensory, spatial/orientation, associative integration, memory/temporal state, predictive processing, affective/modulatory, motor planning and motor execution.

Sparse recurrent configurable topology is required; avoid all-to-all wiring by default.

| Stage | Neurons | Purpose |
|---|---:|---|
| N1 | 1 | Complete physical neuron |
| Pair/quartet | 2–4 | Synaptic interface |
| Micro-connectome | 16 | Recurrent local plasticity |
| Regional | 64 | Sensory/associative/motor integration |
| Expanded | 128 | Memory, prediction, modulation |
| Initial full target | 512 | Integrated research connectome |

These are engineering targets, not demonstrated capacities. Every expansion requires measured power, area, signal integrity, cross-talk, thermal, calibration and stability analysis.

## 8. DSAG research pathway

Retain Dual-Soma Axonal Graft as an advanced variant: independently maintained Soma A and Soma B, bidirectional coupling and a configurable delayed axonal-dendritic feedback path. A provisional hypothesis assigns rapid/local processing to A and contextual/temporal processing to B; this must be tested, not assumed. DSAG does not replace the standard six-channel soma; it adds a second pathway. Document stability and compare against single-soma controls. Do not describe it as a validated biological mechanism.

## 9. Sensory system

- **Vision:** photodiodes, spatial light channels, contrast and analogue motion/temporal change. Investigate focal-plane/event-based sensors later; avoid a digital image-processing pipeline as core perception.
- **Audition:** microphone amplification, analogue filters, envelope and temporal channels; multiple microphones for directional comparison.
- **Touch:** pressure-sensitive transducers, tactile arrays and bumper/contact switches.
- **Proximity:** infrared and/or ultrasonic transducers with analogue receiver/conditioning.
- **Inertial:** conditioned acceleration and angular-rate signals.
- **Proprioception:** wheel encoders, motor-current feedback and future joint-position sensors.
- **Environment:** thermistors and other analogue transducers.

Digital sensor modules require an explicit boundary and must not conceal a digital neural processor.

## 10. Mobile embodiment

Initial platform: six-wheel low-speed rover, low centre of gravity, guarded wheels, accessible electronics enclosure, modular sensor mast and emergency stop. Differential/skid steering is suitable for the first embodiment.

Motor planning/control signals originate in analogue neural/motor circuits. Independent driver electronics provide power amplification, current limiting and safe shutdown. Encoder/current feedback returns to proprioceptive populations.

For a differential-drive abstraction:

[
V_L=V_{forward}+V_{turn},quad V_R=V_{forward}-V_{turn}
]

Real drivers require calibrated ranges, deadbands, slew/current limits and safe defaults.

## 11. Power and safety

Separate sensitive analogue supplies from motor power and high-current returns. Define all rails, references, common-mode ranges, connector pinouts, decoupling, filtering, thermal limits and fault states before board release.

Battery operation requires a suitable BMS, fuse, overcurrent and undervoltage protection, thermal monitoring, correct wiring/connectors and emergency isolation. Begin with a current-limited bench supply. Test motors with wheels raised or restrained before mobile testing.

## 12. Development sequence

1. Freeze N1 interfaces and acceptance criteria.
2. Model and bench-test one complete N1.
3. Connect 2–4 neurons; test synaptic transmission/timing.
4. Expand to a 16-neuron micro-connectome.
5. Add modulation and plasticity; quantify repeatability.
6. Add analogue sensory front ends.
7. Scale through 64 and 128 toward the 512 target.
8. Build analogue motor circuits and test on a restrained chassis.
9. Integrate the rover and validate in controlled environments.
10. Investigate integrated analogue ICs, memristive synapses and further scaling.

## 13. Non-negotiable constraints

- No silent feature loss.
- No digital neural inference in operational behaviour.
- Every approximation is explicit and traceable.
- Every capability claim requires reproducible evidence.
- Safety interlocks remain independent.
- Circuit/connectome interfaces are versioned.
- Preserve previous specifications and experimental data.
