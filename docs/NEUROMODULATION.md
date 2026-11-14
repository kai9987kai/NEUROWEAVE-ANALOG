# Neuromodulation and Receptor-Inspired Circuits

**Status:** Proposed analogue abstraction.

Dedicated analogue control signals and local response circuits influence excitability, gain, time constants, synaptic conductance or plasticity. They are not actual neurotransmitters or biological receptors.

| Engineering signal | Research role | Candidate electrical effect |
|---|---|---|
| Dopamine-like | Reward/learning | Plasticity gate, eligibility weighting |
| Serotonin-like | Slow state/stability | Slow gain or excitability |
| Noradrenaline-like | Arousal/responsiveness | Gain and threshold |
| Acetylcholine-like | Attention/learning | Sensory gain and plasticity gating |
| Octopamine-like | State-dependent | Population-specific gain |
| Endocannabinoid-like | Local/retrograde | Local synaptic efficacy update |
| GABA-like | Inhibition | Inhibitory conductance |
| Glutamate-like | Excitation | Excitatory conductance |

Retain response profiles inspired by D1/D2, 5-HT1A/5-HT2A, adrenergic, muscarinic, octopamine and CB1 families. Each profile needs a transfer curve, range, time response, target population and interaction specification.

Use regional modulation buses plus local circuits; one global voltage should not necessarily have identical effects in every population. A candidate relation is:

[
g_{effective}=g_{base}f(V_{mod},V_{context})
]

Define and measure (f) per circuit. Bound ranges, include saturation/decay/recovery and test single and combined modulators with disconnected controls.
