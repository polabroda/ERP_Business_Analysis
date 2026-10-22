# TO-BE Process – Proposed Target State

```mermaid
flowchart TD
  A[Register customer/site work order] --> B[Unique work-order ID assigned]
  B --> C{Operations approves scope?}
  C -- No --> D[Return for correction / cancel with reason]
  D --> A
  C -- Yes --> E[Dispatcher assigns technician/date]
  E --> F[Technician executes work]
  F --> G[Record labor, materials and evidence]
  G --> H{Completion records sufficient?}
  H -- No --> G
  H -- Yes --> I[Operations manager accepts work]
  I --> J{Billing references complete?}
  J -- No --> K[Finance resolves missing data]
  K --> J
  J -- Yes --> L[Export invoice-ready record with stable reference]
  L --> M{Accounting acknowledgment/reconciliation?}
  M -- Failed --> N[Controlled retry / exception handling]
  N --> M
  M -- Success --> O[Mark as billed]
```

**Status:** `DESIGN PROPOSAL`, not a validated, implemented or tested workflow. The exact acknowledgment and retry mechanism is **TO VERIFY** with the accounting system.

See [process analysis](../04_process_analysis.md) and [requirements](../03_requirements_catalogue.md).
