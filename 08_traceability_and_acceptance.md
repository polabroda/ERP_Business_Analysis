# 08 – Requirements Traceability and Draft Acceptance Scenarios

These are proposed scenarios to support **future** stakeholder validation and UAT planning. They have **not been executed**, and no actual ERP has been configured.

## Traceability Matrix (selected Must requirements)

| Business objective | Requirement ID | Process step | Draft test | Result |
|---|---|---|---|---|
| OBJ-01 | BR-001, FR-001 | Register order | UAT-01 | NOT RUN |
| OBJ-04 | FR-002, FR-003 | Approve and schedule | UAT-02 | NOT RUN |
| OBJ-03 | FR-004, FR-005, FR-007 | Record and accept work | UAT-03 | NOT RUN |
| OBJ-02 | BR-002, FR-008 | Billing handoff | UAT-04 | NOT RUN |
| OBJ-02 | FR-009, NFR-004 | Repeated billing export | UAT-05 | NOT RUN |
| OBJ-03 | FR-012, NFR-002 | Audit and approvals | UAT-06 | NOT RUN |
| OBJ-03 | NFR-001 | Role-based access | UAT-07 | NOT RUN |

## UAT-01 – Unique Work Order Reference

**Precondition:** authorized intake user; customer and site exist.

**Steps:** create two service orders for the same customer/site; save and open both records.

**Expected:** each order has a distinct immutable ID, and customer/site links are retained.

**Related:** `BR-001`, `FR-001`.

## UAT-02 – Dispatch Control

**Precondition:** new Draft order.

**Steps:** attempt to schedule before approval; approve; schedule with technician and date.

**Expected:** unauthorized transition blocked; approved order may be scheduled; owner and state are visible.

**Related:** `FR-002`, `FR-003`.

## UAT-03 – Missing Completion Details

**Precondition:** assigned job at `Work Done`, missing required labor record.

**Steps:** operations manager attempts acceptance; technician supplies labor and either material usage or explicit N/A; retry.

**Expected:** first acceptance blocked with actionable reason; second is permitted if checks pass.

**Related:** `FR-004`, `FR-005`, `FR-007`.

## UAT-04 – Controlled Billing Release

**Precondition:** accepted job with required billing references.

**Steps:** finance generates invoice-ready export; inspect record identifiers and required fields.

**Expected:** only accepted work is exported; stable work-order and billing references are included.

**Related:** `BR-002`, `FR-008`.

## UAT-05 – Duplicate Export

**Precondition:** UAT-04 completed once for the same unchanged billing version.

**Steps:** repeat billing export/retry.

**Expected:** system prevents a new independent billing item; same idempotency/business key supports reconciliation. Exact acceptance depends on accounting contract.

**Related:** `FR-009`, `NFR-004`.

## UAT-06 – Audit History

**Precondition:** order has been assigned and approved.

**Steps:** open history; inspect author/time of status transitions and acceptance.

**Expected:** significant decisions are recorded and available to permitted roles.

**Related:** `FR-012`, `NFR-002`.

## UAT-07 – Separation of Duties

**Precondition:** technician account without manager/finance permissions.

**Steps:** technician attempts acceptance and billing release.

**Expected:** access denied, no state change occurs, action is logged if security policy requires it.

**Related:** `NFR-001`, `FR-007`, `FR-008`.

## Outstanding Evidence Before Real Testing

- Accepted role and permission matrix
- Approved accounting interface and reconciliation contract
- Sample sanitized customer/site and work-order data
- Approved mandatory fields by job category
- Agreed acceptance owners and actual system environment

**All execution statuses are `NOT RUN`.** These artifacts illustrate analytical preparation, not QA execution or system deployment.
