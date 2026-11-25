# Architectural evaluation scenarios

Analytical scenarios from Table 11 of the revised manuscript. These are expected responses and acceptance conditions, not executed tests.

| ID | Scenario | Requirements | Interfaces | Expected response and acceptance condition |
|---|---|---|---|---|
| S1 | Authorized credit issuance | TC1, TC2, TC3, CI1 | IF3, IF4, IF5, IF6, IF7 | Issuance is completed only after evidence, authorization, validation and finality conditions are satisfied. |
| S2 | Duplicate issuance or reuse of retired credits | TC3, TC5 | IF3, IF7 | Duplicate issuance and unauthorized reuse are rejected without producing additional valid credits. |
| S3 | Unauthorized access to sensitive information | GP1, GP2 | IF1, IF2, IF9 | Access is denied according to identity, authorization and confidentiality policies. |
| S4 | Incorrect or contested MRV evidence | TC2, TC4, CI2 | IF6, IF7, IF9, IF10 | Affected records are identifiable; authorized corrections preserve audit history; unresolved evidence is not approved. |
| S5 | Reported reversal event | TC4, IT2 | IF7, IF8, IF10 | Event and applicable accounting adjustments are traceable to affected project and credit records. |
| S6 | External registry discrepancy | TC5, IT1, IT2 | IF7, IF10 | Conflicting identifiers, quantities or states are identified without declaring unresolved records reconciled. |
| S7 | Unauthorized modification of safeguard records | GP1, GP2, GP3, CI2 | IF1, IF8, IF9 | Unauthorized modifications are rejected; authorized changes preserve accessible audit history subject to confidentiality policies. |
| S8 | Incompatible technological configuration | CI1, IT3 | IF1–IF10 | Configuration is inadmissible when applicable contracts, requirements or constraints cannot be satisfied. |

Further implementation-level assessment is needed for coupling, contract preservation, semantic and operational interoperability, and independent validation of requirement completeness and satisfaction.
