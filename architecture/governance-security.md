# Governance, security and stakeholder inclusion

Technological governance concerns network participation, credential management and protocol operation. Institutional governance concerns stakeholder responsibilities, environmental assessments, credit authorization and dispute resolution. Assign explicit responsibilities for granting and revoking permissions, approving credit operations and resolving conflicting information. Preserve traceability of authorization changes and institutional decisions.

## Preliminary security considerations

| Threat | Relevant architectural responsibilities |
|---|---|
| Unauthorized access | Identity, authorization, information protection |
| Compromised credentials | Credential management, revocation, authorization |
| Malicious participants | Consensus under explicit fault assumptions, validation and audit |
| Manipulated external information | Source identification, provenance, external assessment |
| Conflicting credit operations | State validation, finality, registry reconciliation |
| Service unavailability | Communication, status reporting, failure handling |

This is a preliminary mapping, not a validated threat model. Establish explicit trust assumptions and security boundaries for each configuration. Distributed agreement does not guarantee the correctness of external information or institutional decisions.

Protect sensitive information through applicable access, disclosure and retention policies, including applicable data protection obligations. Protected off-chain storage and selective disclosure are candidate mechanisms.

Support authorized access to consultation, consent, benefit-sharing and grievance records for relevant stakeholders, including local communities and Indigenous Peoples. Recording these processes does not establish effective participation or institutional compliance.

Requirements: GP1–GP3, CI1–CI2. See [interface contracts](../interfaces/interface-contracts.md).
