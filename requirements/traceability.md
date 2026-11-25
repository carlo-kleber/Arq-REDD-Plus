# Requirements-to-Component Traceability

The functional decomposition presented in the preceding specification documents establishes a correspondence between the requirements identified during domain characterization and the architectural components of Arq-REDD+. While Table 4 of the accompanying manuscript identifies the architectural layers associated with each requirement, the following table refines this correspondence by identifying the individual functional components responsible for contributing to its realization.

| ID | Requirement | Network | Consensus | Application |
|---|---|---|---|---|
| TC1 | Versioning of project documentation, emission baselines, additionality evidence, and methodologies | — | — | A1, A5 |
| TC2 | Traceability of MRV evidence and validation and verification decisions | N1, N2 | — | A2, A5, A6 |
| TC3 | Management of carbon credit life-cycle states | — | C1, C3, C4 | A3, A4 |
| TC4 | Recording of reversals and associated accounting adjustments | — | C3 | A3, A4, A7 |
| TC5 | Prevention of duplicate issuance and repeated credit use within the system | — | C1 | A3, A4 |
| GP1 | Stakeholder identification and role-based authorization | N2, N3 | — | A4 |
| GP2 | Protection of sensitive information | N3, N4 | — | A4, A5 |
| GP3 | Traceability of socio-environmental safeguards, benefit-sharing arrangements, and grievance resolution | N4 | — | A4, A5 |
| CI1 | Agreement on the valid state of the distributed ledger | — | C2, C4 | — |
| CI2 | Integrity and auditability of recorded information | — | C3 | A5 |
| IT1 | Integration with external MRV systems and carbon registries | N1 | — | A6 |
| IT2 | Reconciliation with external registries and jurisdictional accounting systems | — | — | A7 |
| IT3 | Compatibility among technological decisions and preservation of architectural responsibilities | N1–N4 | C1–C4 | A1–A7 |

*Notation:* N1–N4, C1–C4, and A1–A7 identify the functional components defined in the [Network Layer](../architecture/network-layer.md), [Consensus Layer](../architecture/consensus-layer.md), and [Application Layer](../architecture/application-layer.md), respectively. A dash indicates that no direct functional responsibility is assigned to the corresponding layer for the requirement under consideration.

The resulting mapping establishes bidirectional traceability. Starting from a requirement, it is possible to identify the functional components intended to contribute to its realization. Conversely, starting from a functional component, it is possible to identify the requirements that motivate its architectural responsibilities.

The correspondence is characterized by many-to-many relationships. A single requirement may depend on multiple functional components distributed across different layers, while a single component may contribute to the realization of several requirements. For example, the management of carbon credit life-cycle states (TC3) requires coordinated responsibilities associated with transaction validation (C1), ledger state management (C3), finality management (C4), carbon credit management (A3), and governance and business rule execution (A4).

The mapping identifies direct functional contributions rather than all possible operational dependencies. For example, although network communication is necessary for distributed agreement, the primary architectural responsibility for establishing agreement is assigned to the Consensus Layer. Consequently, the absence of a direct association in the table does not imply the absence of interactions or dependencies involving the corresponding layer.

Requirement IT3 has a cross-cutting nature because compatibility among technological decisions and preservation of architectural responsibilities concern the architecture as a whole. Its realization depends on the combined configuration of functional components, technological decision points, interface contracts, and compatibility constraints, rather than on the behavior of an isolated component.

The mapping indicates that all thirteen identified requirements have at least one associated functional component and that all fifteen functional components contribute to at least one requirement other than IT3. This result establishes structural coverage of the requirements catalogue within the proposed architectural decomposition.

However, the existence of a correspondence between a requirement and one or more functional components does not independently demonstrate that the requirement has been satisfied. Such an assessment requires examining the specified component behavior, interface contracts, compatibility constraints, and acceptance criteria under relevant operational scenarios. The traceability mapping therefore provides a basis for the subsequent architectural evaluation rather than constituting sufficient evidence of requirement satisfaction.
