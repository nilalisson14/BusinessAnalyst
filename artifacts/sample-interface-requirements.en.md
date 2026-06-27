# Sample Artifact — Interface Requirements

> [🇧🇷 Português](sample-interface-requirements.pt.md) · [← Back to index](../README.en.md)

An **anonymized** example of interface-requirements specification in a table — the level of detail I deliver to guide development without ambiguity.

---

## IR — Responsible-party change screen

| Field | Type | Criterion | Required |
| --- | --- | --- | --- |
| Current responsible | Display | Shows the item's current responsible party | N |
| Search responsible | Search | Finds a new eligible internal user by name or key | Y |
| Justification | Text | Free text justifying the change | Y |
| Change | Button | Confirms the operation and triggers notifications | N/A |
| Close | Button | Cancels the action and ends the feature | N/A |

## IR — Conditional classification field

| Prescription type | Options shown | Behavior |
| --- | --- | --- |
| Common | Two options | Both unchecked; single mandatory selection |
| Special control | One option | Pre-selected and locked (not editable) |

## Why this artifact

It demonstrates translating business rules into verifiable interface behavior: each field with explicit type, criterion, and requiredness, and the handling of conditional states. This is what reduces back-and-forth between business, design, and development.
