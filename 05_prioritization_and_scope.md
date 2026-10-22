# 05 – Prioritization and Scope Definition

## Method

MoSCoW categories are applied as proposed analysis priorities:

- **Must:** needed for a controlled work-order-to-billing lifecycle and minimum governance.
- **Should:** valuable for usability, continuity and process completeness but potentially deferrable.
- **Could:** worthwhile enhancements once core data and workflow are stable.
- **Won't (MVP):** deliberately deferred beyond the first release.

## Proposed Scope by Phase

| Phase | Requirement IDs | Business value / rationale | Exit evidence required |
|---|---|---|---|
| Phase 0 – Readiness | BR-001–BR-003, NFR-001, NFR-002, NFR-004, NFR-005 | Confirm master data, billing contract, responsibilities and controls | Approved baseline and integration feasibility |
| Phase 1 – Core MVP | FR-001–FR-005, FR-007–FR-009, FR-012, NFR-001, NFR-002, NFR-004, NFR-005, BR-001, BR-002 | Controlled order processing and invoice-ready handoff | UAT evidence, migration checks, recovery rehearsal |
| Phase 1.1 – Operational improvements | FR-006, FR-010, FR-011, BR-003, NFR-003 | Better usability, evidence and exception handling | Prioritized backlog and process sign-off |
| Phase 2 – Expansion | FR-013, FR-014 | Replenishment and operational analytics | Stable core data and adoption |
| Outside MVP / candidate future release | FR-015 | Customer portal depends on stabilized internal processes | Separate business case |

**Sequencing note:** Although BR-003 is categorized `Should`, the outage reconciliation control must still be resolved during readiness if business continuity policy requires it; it must not be left unaddressed simply because it is outside the main MVP delivery list.

## MVP Scope Acceptance Gates

1. Customer and site identifiers have an agreed source of truth.
2. Approval rules and access matrix are agreed by accountable business owners.
3. Required labor/material fields have been signed off by operations and finance.
4. An accounting integration format and duplicate-prevention approach are validated.
5. Historical data has been profiled and a migration strategy decided.
6. Critical business scenarios, including exceptions, are demonstrated and tested.
7. Recovery and manual fallback are documented.

## Explicit Non-Commitments

The proposed MVP does **not** include: payroll, a replacement accounting ledger, end-to-end procurement, e-commerce, advanced CRM, customer portal, or a claim that a selected ERP is ready for production.

## Delivery Strategy

Conduct requirements confirmation and market assessment before procurement decisions. Reassess MVP scope after a fit-gap review and before any implementation commitment. No vendor has been evaluated or selected in this case.
