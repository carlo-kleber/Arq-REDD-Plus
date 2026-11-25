# Carbon credit life cycle

Logical specification based on Section 5.7 and Table 8 of the revised manuscript.

| Operation | Initial state | Principal conditions | Resulting state or effect |
|---|---|---|---|
| Issuance | Not issued | Verified emission reductions, authorized issuance, unique issuance entitlement and applicable registry approval | Active credit with unique identifier |
| Transfer | Active | Authorized holder, eligible recipient and sufficient available quantity | Active credit with updated ownership |
| Retirement | Active | Authorized request, available quantity and applicable claim conditions | Retired credit unavailable for ordinary transfer or reuse |
| Cancellation or invalidation | Applicable existing state | Authorized institutional decision and applicable registry rules | Cancelled or invalidated credit with preserved history |
| Reversal accounting | Applicable credit or project records | Recorded reversal event and applicable non-permanence procedures | Accounting adjustment or buffer-related action, as applicable |

## Logical workflow

1. Register project and methodology (IF5, IF8).
2. Submit MRV evidence and register external assessments (IF6).
3. Request authorized issuance (IF7).
4. Validate and establish finality (IF3, IF4).
5. Manage circulation and retirement (IF7).
6. Handle exceptional events and reconciliation (IF7, IF8, IF10).

Identity, communication, audit and external reconciliation responsibilities apply throughout. Quantity conservation and prevention of duplicate issuance must be preserved across concurrent or repeated requests, including requests with different operation identifiers. Reversal accounting does not necessarily imply cancellation of individual credits.

See [interface contracts](../interfaces/interface-contracts.md). This is a logical workflow, not a deployed implementation.
