# Feature Preservation and Traceability

**Purpose:** prevent accidental regression or silent loss while translating software research concepts into hardware.

## Status definitions

- **Preserved:** retained in target architecture.
- **Mapped:** candidate physical mechanism proposed.
- **Modelled:** circuit simulation archived.
- **Bench-tested:** physical implementation has reproducible bench evidence.
- **Integrated:** validated in a connected network/robot.
- **Open dependency:** adequate physical implementation not yet established.

| Feature | Candidate mapping | Initial status |
|---|---|---|
| Four dendrites | Four analogue dynamic circuits | Preserved / mapped |
| Six soma channels | Six analogue channel paths | Preserved / mapped |
| Membrane state | Capacitor/integrator | Preserved / mapped |
| Adaptive threshold | Slow integrator + comparator reference | Preserved / mapped |
| Refractory period | RC timing and gating | Preserved / mapped |
| Calcium-like state | Bounded leaky integrator | Preserved / mapped |
| Axonal branches | Pulse distribution stages | Preserved / mapped |
| Excitatory/inhibitory synapses | Conductance/current stages | Preserved / mapped |
| Neuromodulation | Local/global analogue control | Preserved / mapped |
| Receptor profiles | Distinct transfer functions | Preserved / mapped |
| STDP | Pre/post pulse trace circuits | Preserved / mapped |
| Eligibility traces | RC state network | Preserved / mapped |
| Long-term memory | Nonvolatile conductance/device research | Preserved / open dependency |
| Structural plasticity | Configurable analogue switching | Preserved / mapped |
| Sparse recurrent connectome | Modular interconnect | Preserved / mapped |
| DSAG | Dual soma and graft feedback | Preserved / research |
| Vision | Photodiode/analogue front end | Preserved / mapped |
| Audition | Microphone/filter channels | Preserved / mapped |
| Touch | Tactile transducers | Preserved / mapped |
| Spatial/proximity | IR/ultrasonic/IMU circuits | Preserved / mapped |
| Proprioception | Encoder/current/IMU signals | Preserved / mapped |
| Motor control | Analogue planning and driver circuits | Preserved / mapped |
| Mobile body | Six-wheel rover | Preserved / planned |

## Change policy

Every change must include requirement ID, existing behaviour and rationale, proposed mapping/limitation, dependent modules, validation experiment, compatibility statement and maintainer decision.

A feature may be deferred, approximated or declared infeasible only with written rationale and an explicit open issue. It must not disappear from this matrix.
