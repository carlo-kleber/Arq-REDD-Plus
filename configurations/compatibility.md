# Compatibility constraints

From Table 9 of the revised manuscript.

| Decision points | Constraint |
|---|---|
| DN1, DN2, DN3 | Exposure and participation satisfy confidentiality and access control. |
| DN2, DN4, DC1 | Identification and admission satisfy consensus eligibility and trust assumptions. |
| DN3, DC1, DA1 | Authorized validators have sufficient information or verifiable evidence to validate state transitions. |
| DC1, DC2 | Confirmation conditions match consensus finality and fault assumptions. |
| DC2, DA1, DA2 | Credit operations respect confirmation conditions, admissible transitions and quantity conservation. |
| DN4, DA1 | Execution enforces stakeholder roles and authorization. |
| DN3, DA3 | Storage, retrieval and disclosure preserve confidentiality, integrity, availability and auditability. |
| DA2, DA4 | Credit identifiers, quantities and states support external registry reconciliation. |
| DA1, DA3, DA4 | External information required for execution is accessible through defined interfaces with provenance and validation procedures. |

These constraints concern design-time admissibility, not seamless post-deployment migration.
