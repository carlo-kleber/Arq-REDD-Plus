# Complementary simulation evaluation

The original experimental materials are maintained in the [authors' original repository](https://github.com/mCaburlao/Arq-REDD-). Consult its README, source code, input data and license. This documentation links to that repository rather than claiming an independently reproduced or verified copy.

The revised manuscript reports two studies using JABS: comparative performance (200 nodes, two simulated hours, ten repetitions with distinct seeds) and scalability (25–400 nodes in increments of 25, one simulated hour, ten repetitions per configuration under identical workload conditions). The Arq-REDD+ instantiation uses PBFT, a five-second configured block interval, and 70% public / 30% private transactions. The original study reports a privacy extension based on Constellation.

| Configuration | Consensus | Block interval (s) | Visibility | TB (s) | CB (MB) |
|---|---|---:|---|---:|---:|
| Arq-REDD+ | PBFT | 5 | Differentiated | 12.4 ± 0.4 | 0.397 ± 0.005 |
| Ambify | PoSA | 3 | Public | 0.438 ± 0.004 | 0.005 ± 0.003 |
| Treecycle | PoS | 60 | Public | 1094 ± 411 | 0.021 ± 0.020 |
| MCO2 | PoS | 15 | Public | 360 ± 26 | 0.024 ± 0.010 |
| Earth Dollar | PoW | 450 | Public | 3060 ± 450 | 0.685 ± 0.100 |
| Cool Earth | PoW | 600 | Public | 6454 ± 2300 | 0.182 ± 0.083 |

Reported means and 95% confidence intervals from the manuscript; interval calculations have not been independently reproduced. TB is mean block finalization time; CB is mean total data volume transmitted during block finalization. Comparators are project-inspired abstractions, not complete project implementations. Results do not isolate the cost of privacy or establish architectural interoperability. No new simulation runs were performed for this documentation.
