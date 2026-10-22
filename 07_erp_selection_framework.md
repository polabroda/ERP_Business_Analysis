# 07 – ERP Solution Evaluation Framework

This is a **proposed evaluation method**, not the result of an actual procurement or supplier demonstration. No real ERP vendors are rated here.

## Recommended Selection Process

1. Validate business, functional and non-functional requirements.
2. Establish mandatory compliance, security and integration constraints.
3. Conduct market screening against documented needs.
4. Issue a standardized RFI to potential vendors.
5. Request scenario-based demonstrations using the same sample cases.
6. Build an evidence-backed fit-gap matrix; price and implementation effort should be considered separately.
7. Review implementation partners, support model, risks, data ownership and total cost of ownership (TCO).
8. Prepare a decision paper, with unresolved gaps and assumptions visible.

## Preliminary Evaluation Criteria

Weights are **illustrative**, subject to sponsor approval.

| Criterion | Weight | Evidence requested |
|---|---:|---|
| Service work-order lifecycle and dispatch | 25% | Demonstration with states and approvals |
| Labor/material capture and operational acceptance | 20% | End-to-end example with exceptions |
| Accounting handoff and duplicate prevention | 20% | Contract / integration walkthrough |
| Data migration and integration capability | 15% | API/file specifications, migration approach |
| Access control, audit and continuity | 10% | Role matrix, security docs, recovery approach |
| Support, partner capacity and lifecycle | 10% | SLA, implementation references, roadmap |
| **Total** | **100%** | |

### Scoring Principle

Use 0–4 per criterion: `0 = unsupported`, `1 = major gap`, `2 = partial/customization`, `3 = largely supported with configuration`, `4 = evidenced standard support`.

**A claimed feature without evidence should be marked `TO VERIFY`, not automatically scored 4.** An unmet Must requirement requires separate escalation even when aggregate scores look favorable.

## Sample Fit-Gap Template (not a vendor rating)

| Requirement | Scenario to show | Vendor response | Evidence link | Gap / change needed | Owner |
|---|---|---|---|---|---|
| FR-001 | Create job against customer/site | TO VERIFY | — | — | Operations |
| FR-007 | Block acceptance if labor missing | TO VERIFY | — | — | Operations |
| FR-008 | Export accepted job for billing | TO VERIFY | — | — | Finance |
| FR-009 | Repeat export without duplicate | TO VERIFY | — | — | Finance + IT |
| NFR-001 | Deny technician billing release | TO VERIFY | — | — | Security |

## Proposed RFI Questions

1. Can standard configuration enforce the proposed work-order state machine, including reversals and cancellation?
2. Which events, approvals, and field changes are audit logged?
3. What fields and identifiers are available in invoice-ready exports?
4. How are retries, acknowledgments and duplicate prevention handled?
5. Which functions require custom development rather than configuration?
6. What migration tooling is included for customer/site and open work orders?
7. Can multiple depots and technician assignments be supported without add-ons?
8. Which recovery objectives and support SLAs can the partner contractually commit to?
9. What will remain the responsibility of the customer after implementation?
10. How are customizations maintained across upgrades, and at what cost?

## Demonstration Script

**Scenario A – standard job:** create customer/site order → approve → schedule → register labor and parts → accept → export once → confirm billed.

**Scenario B – exception:** attempt acceptance without labor → system rejects → complete record → accept.

**Scenario C – duplicate prevention:** re-run the same billing export and demonstrate unchanged business identifier and reconciliation outcome.

**Scenario D – permissions:** technician tries to accept a job and release it for billing; actions must be restricted as agreed.

## TCO Categories to Compare

Licenses/subscriptions, implementation, integration, migration, customization, training, infrastructure, support, upgrades, partner dependence, and internal administration. Do not compare license price alone.

## Selection Conclusion

**No solution recommendation is made.** Completing a real selection would require validated requirements, written supplier responses, demonstrated workflows, tested integration assumptions and an approved commercial analysis.
