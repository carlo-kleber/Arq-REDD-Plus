# Contrasting technological configurations

From Table 10 of the revised manuscript. These are candidate configurations, not two validated implementations.

| ID | Configuration A | Configuration B |
|---|---|---|
| DN1 | Differentiated transaction visibility | Public ledger records with protected external data |
| DN2 | Authorized consensus participants | Open participation subject to protocol eligibility |
| DN3 | Restricted propagation and protected transaction data | Cryptographic commitments and protected off-chain storage |
| DN4 | Institutional credentials and cryptographic identities | Cryptographic identities associated with authorized domain credentials |
| DC1 | PBFT | Proof of Stake |
| DC2 | Protocol-defined deterministic finality | Finality defined by selected PoS protocol |
| DA1 | Combined on-chain and off-chain execution | Smart contracts combined with external institutional assessments |
| DA2 | Identifiable credit records or batches | Tokenized credit records or batches |
| DA3 | Combined ledger and protected external storage | Public ledger commitments and protected off-chain storage |
| DA4 | Authenticated APIs | Authenticated APIs and oracle mechanisms |

Both configurations are intended to preserve architectural responsibilities and contracts, subject to [compatibility constraints](compatibility.md). Public plaintext disclosure of protected information is incompatible. Configuration A requires sufficient validation evidence despite restricted visibility. Neither configuration independently establishes external registry consistency or environmental integrity. The simulation addresses only selected network and consensus aspects of A.
