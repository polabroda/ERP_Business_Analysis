# 01 – Business Context and Problem Definition

## Organization (fictional)

**Aster Field Services** provides scheduled and urgent maintenance services to business customers through two depots. The company has approximately 85 employees, including technicians, dispatchers, warehouse staff, account managers, and finance personnel. All figures and practices below are synthetic scenario assumptions.

## Problem Statement

Customer requests are registered in a shared mailbox, work orders are assigned in spreadsheets, technicians return handwritten notes, and finance receives incomplete billing details by email. Because a common work-order identifier is not consistently used, teams may disagree about job status, time spent, and materials consumed. There is no reliable audit trail for approvals.

## Business Objectives

| ID | Objective | Proposed indicator | Illustrative target (to validate) |
|---|---|---|---|
| OBJ-01 | Make work orders traceable across teams | Share of orders with one cross-team ID | 100% for new orders |
| OBJ-02 | Reduce billing handoff delays | Median time from approved work to invoice-ready export | ≤ 2 business days |
| OBJ-03 | Improve completeness of operational records | Orders with accepted labor and materials records | ≥ 95% |
| OBJ-04 | Improve status transparency | Orders with current status and assigned owner | ≥ 98% |

**Important:** no baseline data has been collected. These targets are placeholders for a future discovery workshop, not achieved results.

## Proposed Project Boundaries

**In scope:** customer/site references, work-order entry, dispatch, technician time, materials consumed, attachments, internal acceptance, billing handoff, role-based permissions, and change history.

**Out of scope for MVP:** replacing payroll or the general ledger; advanced CRM; automated replenishment; mobile offline mode; multi-country tax logic; customer self-service portal.

## Constraints and Assumptions

- A separate accounting solution remains in use during the MVP.
- Finance prefers an export-based integration initially; the file contract is **not yet defined**.
- Emergency work must be possible during temporary system outages.
- Any historical-data migration requires profiling and ownership decisions.
- Estimated volumes for discovery: 300 work orders/month and 20 concurrent internal users. **Unverified scenario inputs.**

## Recommended Next Evidence

1. Sample anonymized order-to-invoice journey and current form templates.
2. Volume and exception statistics from operations and finance.
3. Existing customer, site, part and supplier identifiers.
4. Information-security, retention and legal requirements.
5. Accounting import specification and reconciliation controls.

## Analytical Conclusion

The first release should focus on a dependable **work-order-to-billing hand-off** instead of attempting a full enterprise transformation in one step. The scope can expand after the core lifecycle, data ownership and financial reconciliation have been confirmed.
