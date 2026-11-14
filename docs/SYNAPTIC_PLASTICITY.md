# Synaptic Plasticity and Physical Memory

**Status:** Proposed; physical learning not yet demonstrated.

## Goals

Adjustable synaptic efficacy, short-term dynamics, timing-dependent updates, modulatory gating, eligibility traces, homeostatic constraints and persistent state.

A conductance abstraction:

[
I_{syn}=g_{syn}(V_{pre}-E_{syn})
]

Specify polarity, range, response, output compliance and isolation.

### Short-term plasticity
RC state circuits may implement transient facilitation/depression or use-dependent gain. These traces are volatile; measure recovery and saturation.

### STDP-like update

[
Delta w =
egin{cases}
A_+e^{-Delta t/	au_+}, & Delta t>0\
-A_-e^{Delta t/	au_-}, & Delta t<0
end{cases}
]

where (Delta t=t_{post}-t_{pre}). Physical implementation may approximate this using pulse width, overlap, charge or analogue state circuits. Characterise the measured update curve.

### Modulator-gated eligibility
Maintain a local eligibility trace after coincident activity; a modulatory signal influences whether/how the weight updates. Test timing, sign, saturation and decay.

### Homeostasis and structural plasticity
Bound conductance and activity-dependent stabilisation to prevent recurrent saturation. Analogue switches or configurable routing may enable/disable pathways; document default states and ensure critical sensory/safety paths are not inadvertently disconnected.

### Long-term retention
Capacitors are volatile and must not be called permanent memory. Evaluate nonvolatile conductance devices, including memristors, only after measuring retention, endurance, variability, programming requirements and temperature dependence. Provide reproducible readout and backup strategy.

### Acceptance tests
Baseline conductance/drift; potentiation/depression curves; update versus timing; repeatability; modulator gating; saturation/recovery; retention; temperature/supply variation; network stability with plasticity enabled.
