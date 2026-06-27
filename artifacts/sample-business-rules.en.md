# Sample Artifact — Business Rules

> [🇧🇷 Português](sample-business-rules.pt.md) · [← Back to index](../README.en.md)

**Anonymized** examples of business rules I specified, across two distinct domains. They demonstrate integrity, compliance, and calculation.

---

## Domain 1 — Access governance (responsible-party change)

| ID | Rule |
| --- | --- |
| BR01 | The system requires registering an acceptance term (conflict-of-interest declaration) before the new responsible party can operate the item. |
| BR02 | The system keeps the previous responsible party's history; the prior term is not deleted, only marked finalized, with date and justification. |
| BR03 | Only one active acceptance term per responsible party is allowed. |
| BR04 | Only active internal users may be linked; no external collaborator, nor the current responsible party, nor anyone with another conflicting role on the same item. |
| BR05 | The change is only allowed for items in eligible states (e.g., Submitted, Published, in Judgment, in Selection). |

## Domain 2 — Hierarchical integrity and calculation (financial)

| ID | Rule |
| --- | --- |
| BR06 | Every item links to a product/subproduct, which links to a component, which links to a cost type of a program. Without a valid association, inclusion is blocked. |
| BR07 | No level may have a value greater than the budget of the level it is associated with. |
| BR08 | Component estimated value = sum of products; product = sum of subproducts; consumed value = sum of items. |
| BR09 | Currency conversion uses the respective program's rate on the operation date. |
| BR10 | A disbursement enters as credit; actual entry requires an internalization operation, declaring the value in foreign and local currency per the date's exchange rate. |

## Why this artifact

It shows two rule types that appear frequently: **governance/compliance** (access control, auditing, conflict of interest) and **data integrity with calculation** (hierarchy, budget limits, conversion). Rules written atomically, verifiably, and traceably.
