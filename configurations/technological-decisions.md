# Technological Decision Points

The separation between invariant architectural responsibilities and configurable implementation choices is realized through technological decision points. These points identify aspects of the architecture for which different implementation alternatives may be considered according to the applicable project requirements and compatibility constraints.

A technological decision point does not necessarily correspond to a single functional component. A decision may affect multiple components, including components belonging to different architectural layers. Conversely, the realization of a functional component may depend on several technological decisions.

The following table summarizes the technological decision points identified in Arq-REDD+, their primary associated functional components, illustrative implementation alternatives, and the architectural responsibilities that must be preserved.

| ID | Decision point | Components | Illustrative alternatives | Invariant responsibilities |
|---|---|---|---|---|
| DN1 | Network visibility | N3, N4 | Publicly accessible records, restricted records, or differentiated visibility | Enforcement of applicable information visibility policies |
| DN2 | Participation permissions | N1, N2, N3 | Open or restricted participation, including role-specific participation policies | Communication and enforcement of network participation policies |
| DN3 | Information protection | N4, A5 | Encryption, selective disclosure, restricted transaction propagation, or trusted execution environments | Protection of sensitive information according to applicable policies |
| DN4 | Identity and authentication | N2, N3, A4 | Cryptographic identities, digital certificates, or external identity management services | Identification and authentication of participants and support for authorization |
| DC1 | Consensus mechanism | C1, C2, C3, C4 | Proof-of-Work, Proof-of-Stake, or Byzantine fault-tolerant voting protocols | Validation and distributed agreement on valid ledger state transitions |
| DC2 | Finality conditions | C4, A3, A4 | Protocol-defined finality, confirmation-depth policies, or other compatible confirmation criteria | Determination and communication of the confirmation status of operations |
| DA1 | Business rule execution | A1, A2, A3, A4 | Smart contracts, off-chain application services, or combined execution | Enforcement of applicable domain-specific rules and operational conditions |
| DA2 | Carbon credit representation | A3, A7 | Individual credit records, batch-based records, or tokenized representations | Identification, traceability, and valid life-cycle transitions of carbon credits |
| DA3 | Data management | A1, A2, A5 | On-chain storage, off-chain repositories, or combined storage | Storage, retrieval, versioning, and auditability of information |
| DA4 | External system integration | A6, A7 | APIs, oracles, messaging services, or other compatible integration mechanisms | Information exchange and support for reconciliation with external systems |

The alternatives presented in the table above are illustrative rather than exhaustive. They are not necessarily mutually exclusive, and their inclusion does not imply that they provide equivalent functionality, security, performance, or operational guarantees.

The technological decision points are also not independent. For example, participation permissions and identity management mechanisms must be compatible with the eligibility and trust assumptions of the selected consensus protocol. Likewise, information protection and data management mechanisms must preserve the availability of the information required for transaction validation and authorized auditing.

The selection of finality conditions depends on the guarantees provided by the consensus mechanism and the operational requirements associated with carbon credit management. Similarly, decisions concerning business rule execution and credit representation must preserve the applicable state transition conditions and support reconciliation with external registries.

The admissibility of an implementation configuration therefore depends not only on the individual suitability of the selected alternatives but also on their combined ability to satisfy the applicable requirements identified in Table 4 of the accompanying manuscript. Compatibility constraints delimit the combinations of alternatives that can preserve the architectural responsibilities and interface contracts of Arq-REDD+.

The agnostic nature of the model is thus associated primarily with design-time flexibility. Different technological configurations may instantiate the same reference architecture, provided that the applicable requirements, architectural invariants, interface contracts, and compatibility constraints are satisfied. This property does not imply that technological alternatives can be replaced after deployment without migration procedures, modifications to implementation components, or reassessment of the resulting configuration.
