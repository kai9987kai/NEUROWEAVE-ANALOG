# Physical Connectome Architecture

**Status:** Proposed modular sparse recurrent network.

## Regional populations

Sensory input; visual; auditory; somatosensory; spatial/orientation; associative integration; memory/temporal state; predictive processing; affective/modulatory; motor planning; motor execution.

## Topology

Use sparse recurrent connectivity with explicitly defined local and long-range pathways; avoid all-to-all wiring by default. Each connection record includes source population/neuron, destination compartment, polarity, conductance range, delay/time response, plasticity rule, modulation dependencies and physical route.

| Stage | Neurons | Objective |
|---|---:|---|
| N1 | 1 | Complete physical neuron |
| Pair/quartet | 2–4 | Synaptic interface |
| Micro-connectome | 16 | Recurrent local plasticity |
| Regional | 64 | Sensory/associative/motor integration |
| Expanded | 128 | Memory, prediction and modulation |
| Initial full target | 512 | Integrated research connectome |

These are targets. Density depends on actual component count and routing.

## Interconnect requirements

Define pinout, voltage/current limits, E/I and modulatory interfaces, local buffering/isolation, differential links where justified, activity/test headers, latency/loading and safe defaults for disconnected boards.

Before each expansion measure power, area, signal integrity, cross-talk, thermal behaviour, calibration, fault isolation and network stability. Neuron count alone does not demonstrate scaling.
