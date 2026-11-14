# NEUROWEAVE-ANALOG

**A research programme for a pure-analogue neuromorphic mobile robot.**

NEUROWEAVE-ANALOG translates a custom multi-compartment neuron and distributed connectome architecture into physical analogue electronic circuits and, ultimately, a mobile robotic platform.

> **Status: architecture specification / pre-prototype.** The architecture and circuit mappings are proposed engineering designs. No physical neuron, connectome, learning mechanism or mobile robot is claimed to have been built or validated unless supported by dated experimental evidence in this repository.

## Vision

Build a mobile robot whose operational sensing, neural integration, synaptic adaptation, internal modulation, memory traces, motor planning and motor control emerge primarily from physical analogue circuits. Conventional digital processors must not perform neural inference or behavioural decision-making in the operational cognitive pathway.

Development computers may be used for circuit design, PCB layout, simulation, offline analysis and data logging. Independent hardware safety mechanisms are permitted and required.

## Core architectural invariants

- Four independent dendritic compartments per standard neuron.
- Six distinct soma processing channels.
- Membrane dynamics, adaptive threshold, spike generation and refractory behaviour.
- Calcium-like slow state, activity adaptation and eligibility traces.
- Axonal distribution, terminal outputs and feedback pathways.
- Excitatory and inhibitory synaptic conductances.
- Neuromodulatory and receptor-inspired modulation.
- Short- and long-term synaptic plasticity, including STDP research.
- Sparse, recurrent and configurable connectome.
- Multimodal sensory pathways.
- Motor planning, motor execution and sensorimotor feedback.
- Dual-Soma Axonal Graft (DSAG) research pathway.
- Persistent physical state and a documented long-term retention strategy.

No feature is silently removed to simplify a prototype. Deviations require a change record and compatibility statement.

## Initial engineering targets

| Milestone | Target | Meaning |
|---|---:|---|
| N1 | 1 complete neuron | Validate four dendrites and six soma channels |
| Micro-connectome | 2–4, then 16 neurons | Recurrent coupling and plasticity |
| Regional network | 64 neurons | Sensory, associative and motor populations |
| Expanded network | 128 neurons | Memory, prediction and modulation |
| Initial full-scale target | 512 neurons | Research target, not an achieved capability |
| Mobile embodiment | Six-wheel rover | Analogue sensorimotor behaviour |

Neuron count is not a performance metric by itself. Component count, board area, connectivity, power, noise, drift, calibration burden and measured behaviour must also be reported.

## Repository map

- `docs/` — architecture, interfaces, safety and roadmap.
- `hardware/` — schematics, PCB sources, BOMs and test records.
- `research/` — literature notes and open technology questions.
- `experiments/` — reproducible protocols and results.
- `simulations/` — circuit-level models and verification, not operational neural inference.
- `robotics/` — chassis, sensors, actuators and integration.

## Start here

1. [Master architecture](docs/MASTER_ARCHITECTURE.md)
2. [Custom neuron architecture](docs/NEURON_ARCHITECTURE.md)
3. [N1 hardware specification](hardware/neuron_n1/README.md)
4. [Feature preservation matrix](docs/FEATURE_PRESERVATION.md)
5. [Development roadmap](docs/DEVELOPMENT_ROADMAP.md)
6. [Experiment template](experiments/EXPERIMENT_TEMPLATE.md)

## Status vocabulary

- **Proposed:** concept documented, not verified.
- **Modelled:** circuit-level simulation exists and is archived.
- **Bench-tested:** physical circuit tested with a reproducible protocol.
- **Integrated:** tested in a connected network or robot.
- **Validated:** acceptance criteria passed with repeatable evidence.

See [status and validation](docs/STATUS_AND_VALIDATION.md).

## Safety

This is a research specification, not a certified build-ready robot design. Validate power, thermal limits, battery protection, motor drivers, signal levels and emergency-stop behaviour before connecting actuators or batteries. Begin with current-limited bench supplies and low-voltage tests.

See [LICENSE](LICENSE) and [CITATION.cff](CITATION.cff).
