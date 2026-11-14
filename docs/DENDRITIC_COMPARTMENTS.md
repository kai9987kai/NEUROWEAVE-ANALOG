# Four Dendritic Compartments

**Status:** Proposed physical mapping.

The four compartments are independent analogue dynamic systems. Each has its own state, time constant, input network and output interface. Interactions occur through documented soma coupling and configurable local feedback.

- **D1 Proximal:** fast local synaptic integration.
- **D2 Distal:** slower or delayed input integration.
- **D3 Apical:** context/top-down and modulatory influence.
- **D4 Basal:** local sensory plus excitatory/inhibitory input.

These are functional engineering labels, not a literal reproduction of biological dendrite morphology.

A candidate leaky-integrator model is:

[
C_idot V_i=sum_j g_{ij}(E_{ij}-V_i)-rac{V_i-V_{rest}}{R_i}
]

The final circuit may use voltage or current mode, provided independence, polarity, range and time response are measured.

| Parameter | D1 | D2 | D3 | D4 |
|---|---|---|---|---|
| Supply/rails | TBD | TBD | TBD | TBD |
| Input range | TBD | TBD | TBD | TBD |
| Time constant | TBD | TBD | TBD | TBD |
| Leak/bias | TBD | TBD | TBD | TBD |
| Synaptic polarity | E/I | E/I | E/I/mod | E/I |
| Output range | TBD | TBD | TBD | TBD |
| Test point | Required | Required | Required | Required |

Tests: independent step and pulse responses, E/I response, cross-coupling, modulatory response, temperature/supply variation and repeatability between modules.
