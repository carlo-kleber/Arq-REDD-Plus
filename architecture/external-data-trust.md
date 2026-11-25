# External data trust and MRV

Source authenticity, information integrity and domain validity are distinct properties.

| Condition | Interfaces | Expected behavior |
|---|---|---|
| Source identification | IF1, IF10 | Associate evidence with an identifiable source and responsible entity. |
| Provenance and integrity | IF5, IF6, IF9 | Associate evidence with project, methodology version and supporting records. |
| Domain assessment | IF6, IF8 | Record decisions originating from entities authorized under the applicable certification and governance framework. |
| Correction and dispute management | IF6, IF9 | Identify inconsistent, contested or superseded evidence and preserve correction history. |

APIs and oracles facilitate information exchange but do not establish factual correctness. Missing, inconsistent or unverified evidence must not be treated as approved for issuance. When accepted evidence is corrected or contested, identify affected credits and apply applicable governance and reconciliation procedures through IF7, IF8 and IF10.

Requirements: TC1–TC4, GP1, GP2, CI2, IT1. Realization depends on the selected configuration and external assessment and governance mechanisms.
