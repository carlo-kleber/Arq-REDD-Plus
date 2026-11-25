# Architectural Interface Contracts

The functional decomposition of Arq-REDD+ establishes the responsibilities assigned to its architectural components. However, the specification of these responsibilities alone is insufficient to determine how the components must interact to satisfy the applicable domain requirements. To complement the functional decomposition, Arq-REDD+ defines architectural interface contracts that specify the expected behavior of interactions among components and between the architecture and external entities.

An architectural interface contract defines the conditions under which an interaction may occur, the information exchanged, the expected outcomes, and the behavior required when the specified conditions cannot be satisfied. These contracts are expressed independently of specific programming languages, communication protocols, data serialization formats, and Blockchain platforms.

Each interface contract is characterized by the following elements:

- *Interface identifier:* a unique identifier that enables the interface to be referenced throughout the architectural specification and evaluation.
- *Participating entities:* the architectural components or external entities involved in the interaction and their respective responsibilities.
- *Operations:* the logical operations supported by the interface.
- *Inputs and outputs:* the information required to perform an operation and the information or status returned as a result.
- *Preconditions:* the authorization, information availability, state, and other conditions required for successful operation execution.
- *Postconditions:* the expected state, information, or observable effects resulting from successful operation execution.
- *Failure behavior:* the expected behavior when an operation cannot be completed successfully.
- *Invariants:* the properties that must be preserved throughout the interaction, according to the applicable architectural requirements.

The interface contracts specify logical interactions rather than mandatory implementation mechanisms. Depending on the selected technological configuration, an interface may be realized through local function calls, smart contract invocations, application programming interfaces, messaging mechanisms, or other compatible mechanisms. An interface contract does not necessarily correspond to an independently deployed service or a publicly accessible endpoint.

The preservation of interface contracts requires more than syntactic compatibility. Alternative implementations must also preserve the meaning of the information exchanged, the applicable operational conditions, the expected state transitions, and the specified failure behavior.

## Identification of Architectural Interfaces

The following table identifies the principal architectural interfaces of Arq-REDD+, their participating functional components, and their associated domain requirements.

| ID | Interface | Components | Purpose | Requirements |
|---|---|---|---|---|
| IF1 | Identity and Authorization | N2, N3, A4 | Identity verification and authorization decisions | GP1, GP2 |
| IF2 | Communication and Transaction Submission | N1, N3, N4, C1, A4 | Protected submission and exchange of operation requests | GP1, GP2, CI1 |
| IF3 | Transaction Validation and Execution | C1, C2, A3, A4 | Validation and execution of admissible state transitions | TC3, TC4, TC5, CI1 |
| IF4 | Ledger State and Finality | C2, C3, C4, A3, A4 | Communication of ledger state and operation confirmation status | TC3, TC4, CI1, CI2 |
| IF5 | Project and Methodology Management | A1, A2, A5 | Management and retrieval of project and methodology records | TC1, TC2 |
| IF6 | MRV Evidence and External Assessment | A1, A2, A4, A5, A6 | Submission, validation, and traceability of MRV evidence and assessments | TC2, TC3, IT1 |
| IF7 | Carbon Credit Life-Cycle Management | A2, A3, A4, A7 | Management of authorized credit-related operations | TC3, TC4, TC5, IT2 |
| IF8 | Governance and Safeguards | N2, A4, A5 | Management of stakeholder roles and socio-environmental records | GP1, GP2, GP3 |
| IF9 | Data Management and Audit | N4, C3, A5 | Protected storage, retrieval, versioning, and auditing of information | TC1, TC2, GP2, GP3, CI2 |
| IF10 | External Integration and Reconciliation | A3, A6, A7 | Information exchange and reconciliation with external systems | TC4, TC5, IT1, IT2 |

The interfaces identified in the table above encompass interactions within individual layers, interactions across architectural layers, and interactions with stakeholders and external systems. They represent the principal logical interactions required to support the architectural responsibilities, rather than an exhaustive enumeration of all possible implementation-level interactions.

Requirement IT3 applies across the entire interface specification because compatibility among technological decisions depends on the preservation of the applicable interface contracts.

## Common Information Elements and Behavioral Properties

To support consistent interpretation across the architectural interfaces, Arq-REDD+ identifies a set of common logical information elements. Depending on the operation, the exchanged information may include:

- *Operation identifier:* an identifier associated with an operation request and its processing history.
- *Participant identifier:* an identifier or credential associated with the requesting or responsible entity.
- *Project identifier:* an identifier associated with the REDD+ project or applicable jurisdictional program.
- *Credit identifier:* an identifier associated with an individual carbon credit or an identifiable batch of credits.
- *Evidence reference:* an identifier or reference associated with supporting documentation, MRV information, or external assessments.
- *Version reference:* an identifier associated with the applicable version of a document, methodology, evidence record, or governance rule.
- *External reference:* an identifier associated with a record maintained by an external registry or information system.
- *Operation status:* information indicating the current processing outcome or confirmation status of an operation.

These information elements define logical semantics rather than mandatory data formats. Their concrete representation depends on the selected technological configuration and the requirements of the interacting systems.

Operation status information must distinguish, where applicable, between submitted, pending, confirmed, rejected, and failed operations. Confirmation must be interpreted according to the finality conditions adopted by the implementation. An unavailable response or an interrupted communication process must not automatically be interpreted as evidence that the corresponding operation has failed or has been successfully completed.

Operations that may modify credit-related records must support the identification of repeated requests and prevent unintended duplicate state transitions. The mechanisms employed to achieve this property depend on the selected implementation and may involve operation identifiers, transaction identifiers, state verification, or other compatible mechanisms.

The interfaces must also preserve the association between operations, responsible entities, applicable rules, and supporting information. Sensitive information must be exchanged and disclosed according to the applicable authorization and confidentiality policies.

## Specification of Interface Contracts

The following contracts specify the principal operations, information exchanged, operational conditions, expected outcomes, and failure behavior associated with each architectural interface.

### IF1 – Identity and Authorization

This interface coordinates the identity and authentication responsibilities of N2, the network access responsibilities of N3, and the domain-specific authorization responsibilities of A4.

- *Operations:* authenticate participants, verify credentials, and evaluate authorization requests.
- *Inputs:* participant identifier or credential, requested operation, applicable role, and relevant authorization context.
- *Outputs:* authentication result, authorization decision, and applicable restrictions.
- *Preconditions:* the required identity information and applicable authorization policies must be available.
- *Postconditions:* an authentication or authorization decision is established according to the applicable policies.
- *Failure behavior:* invalid, expired, revoked, or insufficient credentials must not result in unauthorized access or operation execution.
- *Invariants:* authentication does not independently imply authorization to execute domain-specific operations. Authorization decisions must respect the applicable role and access policies.

### IF2 – Communication and Transaction Submission

This interface coordinates the submission and exchange of operation requests among the Network, Consensus, and Application layers.

- *Operations:* submit operation requests, exchange messages, and retrieve submission status.
- *Inputs:* operation identifier, operation data, participant information, and applicable protection requirements.
- *Outputs:* submission acknowledgement, request identifier, or communication status.
- *Preconditions:* the request must satisfy the applicable communication, network access, and information protection conditions.
- *Postconditions:* an admissible request is delivered to the appropriate processing component or assigned an identifiable pending status.
- *Failure behavior:* malformed requests and unauthorized submissions must be rejected. Communication interruptions must be reported or handled without assuming successful operation execution.
- *Invariants:* information protection requirements must be preserved during communication. Submission acknowledgement does not imply transaction validation or finality.

### IF3 – Transaction Validation and Execution

This interface coordinates protocol-level transaction validation, distributed agreement, and the execution of applicable domain-specific rules.

- *Operations:* evaluate operation admissibility, validate proposed state transitions, and process admissible transactions.
- *Inputs:* operation identifier, transaction data, applicable ledger state, authorization information, and domain-specific validation conditions.
- *Outputs:* validation result, proposed or accepted state transition, and processing status.
- *Preconditions:* the operation must satisfy the applicable authorization, protocol, and domain-specific validation conditions.
- *Postconditions:* an admissible state transition is processed according to the selected execution and consensus mechanisms.
- *Failure behavior:* invalid or unauthorized operations must not produce an accepted state transition. Repeated requests must not produce unintended duplicate effects.
- *Invariants:* accepted state transitions must comply with the applicable protocol and domain-specific rules. Protocol-level validation does not independently establish the environmental validity of external information.

### IF4 – Ledger State and Finality

This interface coordinates the communication of ledger state and transaction confirmation information between the Consensus and Application layers.

- *Operations:* retrieve ledger state, query operation status, and communicate confirmation or finality information.
- *Inputs:* operation identifier, transaction identifier, credit identifier, or relevant ledger state reference.
- *Outputs:* ledger state information, confirmation status, and applicable finality information.
- *Preconditions:* the requested information must be identifiable and accessible according to the applicable policies.
- *Postconditions:* the requesting component receives the available state and confirmation information according to the selected consensus mechanism.
- *Failure behavior:* unavailable, inconsistent, or insufficient confirmation information must be reported without incorrectly classifying the operation as finalized.
- *Invariants:* an operation must not be treated as finalized before satisfying the applicable finality conditions. Changes affecting previously observed non-final states must be communicated or made detectable.

### IF5 – Project and Methodology Management

This interface coordinates the management and retrieval of project documentation and methodological information.

- *Operations:* register project documentation, register methodology versions, update authorized records, and retrieve applicable information.
- *Inputs:* project identifier, documentation, methodology reference, version information, and responsible entity.
- *Outputs:* record identifier, version reference, registration status, or requested documentation.
- *Preconditions:* the requesting entity must be authorized, and the required documentation and identification information must be available.
- *Postconditions:* the accepted documentation is associated with the corresponding project and applicable methodology version.
- *Failure behavior:* unauthorized or incomplete registration requests must be rejected or identified as pending. Inconsistent version information must be reported.
- *Invariants:* authorized updates must preserve the traceability of previous versions and the association between project decisions and applicable methodological information.

### IF6 – MRV Evidence and External Assessment

This interface coordinates the exchange and management of MRV evidence, supporting documentation, and external validation and verification decisions.

- *Operations:* submit MRV evidence, register assessment decisions, retrieve supporting information, and register authorized corrections.
- *Inputs:* project identifier, evidence reference, source information, methodology version, responsible entity, and assessment information.
- *Outputs:* evidence identifier, assessment status, validation result, or correction reference.
- *Preconditions:* the required evidence and provenance information must be available, and the submitting or assessing entity must satisfy the applicable authorization conditions.
- *Postconditions:* accepted evidence and assessment decisions are associated with the corresponding project, methodology, responsible entities, and supporting records.
- *Failure behavior:* missing, inconsistent, unauthorized, or unverifiable information must not be treated as approved evidence. Such information must be rejected, flagged, or assigned a pending status according to the applicable procedures.
- *Invariants:* evidence provenance and assessment history must remain traceable. Authorized corrections must not silently replace the records associated with previous decisions.

### IF7 – Carbon Credit Life-Cycle Management

This interface coordinates the execution of domain-specific operations associated with carbon credit management.

- *Operations:* request credit issuance, transfer, retirement, and, where applicable, cancellation, invalidation, or reversal-related accounting adjustments.
- *Inputs:* operation identifier, project identifier, credit identifier or proposed credit representation, applicable quantity, authorization information, and supporting evidence or external references.
- *Outputs:* operation status, credit identifier, updated credit state, or accounting adjustment reference.
- *Preconditions:* the requested operation must satisfy the applicable authorization, evidence, credit state, and governance conditions.
- *Postconditions:* a successfully completed operation produces an admissible credit state transition or accounting adjustment according to the applicable rules and finality conditions.
- *Failure behavior:* unauthorized operations, invalid state transitions, duplicate issuance requests, and attempts to reuse retired credits must be rejected. Unresolved external dependencies must not be treated as satisfied conditions.
- *Invariants:* credit-related operations must preserve identification, traceability, and applicable accounting consistency. Retirement must prevent subsequent ordinary transfer or reuse of the corresponding credit.

### IF8 – Governance and Safeguards

This interface coordinates the management of stakeholder roles, governance decisions, and socio-environmental records.

- *Operations:* register or update stakeholder roles, record governance decisions, and manage applicable consultation, consent, benefit-sharing, and grievance records.
- *Inputs:* stakeholder identifier, project identifier, governance rule reference, supporting documentation, and authorization information.
- *Outputs:* governance record identifier, updated role or policy information, or operation status.
- *Preconditions:* the requesting entity must possess the applicable authorization, and the required supporting information must be available.
- *Postconditions:* accepted governance and safeguard records are associated with the corresponding project, responsible entities, and applicable rules.
- *Failure behavior:* unauthorized changes must be rejected. Incomplete or disputed information must not automatically be interpreted as evidence of compliance.
- *Invariants:* governance decisions and socio-environmental records must remain traceable and accessible according to the applicable authorization and confidentiality policies.

### IF9 – Data Management and Audit

This interface coordinates the protected storage, retrieval, versioning, and auditing of project-related information.

- *Operations:* store records, retrieve information, verify record integrity, register authorized corrections, and retrieve audit information.
- *Inputs:* record identifier, information or evidence reference, version information, authorization context, and applicable protection requirements.
- *Outputs:* storage reference, requested information, integrity verification result, or audit record.
- *Preconditions:* the requesting entity must satisfy the applicable access policies, and the required storage or retrieval mechanisms must be available.
- *Postconditions:* accepted records are stored or retrieved according to the applicable integrity, versioning, and information protection requirements.
- *Failure behavior:* unauthorized access, unavailable records, and detected integrity inconsistencies must be reported or handled according to the applicable procedures.
- *Invariants:* information integrity, confidentiality, and authorized auditability must be preserved. A successful integrity verification does not independently establish the factual correctness of the corresponding information.

### IF10 – External Integration and Reconciliation

This interface coordinates information exchange and reconciliation between Arq-REDD+ and external systems, including carbon registries and jurisdictional accounting systems.

- *Operations:* exchange external records, retrieve registry information, associate internal and external identifiers, compare accounting records, and register reconciliation outcomes.
- *Inputs:* project identifier, credit identifier, external record identifier, credit state, accounting information, and applicable authorization references.
- *Outputs:* external information, reconciliation status, discrepancy report, or accounting adjustment reference.
- *Preconditions:* the external source must be identifiable, and the information required for the corresponding exchange or reconciliation procedure must be available.
- *Postconditions:* exchanged information and reconciliation outcomes are associated with the corresponding internal and external records.
- *Failure behavior:* unavailable external services, inconsistent identifiers, conflicting credit states, and unresolved accounting discrepancies must be identified and handled according to the applicable governance procedures.
- *Invariants:* unresolved discrepancies must not be represented as successfully reconciled records. Internal ledger consistency must not be interpreted as sufficient evidence of consistency across independent external systems.

## Interface Compatibility and Requirement Traceability

The interface contracts establish a behavioral complement to the structural traceability presented in the [requirements-to-component traceability table](../requirements/traceability.md). While the functional components identify the responsibilities associated with each requirement, the interfaces specify the conditions under which these responsibilities interact.

The correspondence presented in the [interface table](#identification-of-architectural-interfaces) associates the twelve domain-specific and infrastructural requirements other than IT3 with one or more architectural interfaces. Requirement IT3 applies to all interface contracts because the preservation of their semantics and behavioral properties constitutes a condition for compatibility among technological decisions.

For example, the management of carbon credit life-cycle states (TC3) involves transaction validation and execution (IF3), ledger state and finality management (IF4), MRV evidence and external assessment (IF6), and carbon credit life-cycle management (IF7). These interfaces specify complementary responsibilities that must be coordinated to support admissible credit-related operations.

Similarly, the protection of sensitive information (GP2) involves identity and authorization (IF1), protected communication (IF2), governance and safeguards (IF8), and data management and audit (IF9). Its realization therefore depends on coordinated behavior across multiple architectural components and cannot be attributed exclusively to a single protection mechanism.

An implementation configuration is compatible with an architectural interface contract when it preserves the applicable information semantics, operational conditions, expected outcomes, failure behavior, and invariants. The concrete technologies employed to realize these properties may differ across configurations.

The preservation of individual interface contracts is necessary but not sufficient to establish the admissibility of an implementation configuration. The selected technological alternatives must also satisfy the compatibility constraints arising from dependencies among components, interfaces, and technological decision points.

The interface specification therefore provides a basis for evaluating architectural configurations and operational scenarios. However, it does not independently demonstrate implementation conformance, operational correctness, or interoperability among independently developed systems. Such properties require further assessment against the applicable requirements and operational conditions.
