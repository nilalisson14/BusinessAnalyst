# Sample Artifact — User Story with BDD/Gherkin

> [🇧🇷 Português](sample-user-story.pt.md) · [← Back to index](../README.en.md)

An **anonymized** example of my user-story writing pattern with BDD acceptance criteria. Based on real regulated-healthcare work, with fictional data.

---

## User story

> **As a** Pharmacy,
> **I need** to look up and record the use of prescriptions issued with system-generated numbering,
> **so that** sanitary control is ensured and improper reuse is prevented.

**Precondition:** a prescription with valid, active numbering exists.
**Actor:** dispensing establishment (pharmacy).
**Postcondition:** numbering marked as used and unavailable for reuse.

## Acceptance criteria (BDD/Gherkin)

```gherkin
Feature: Prescription dispensing and validation by the pharmacy

  Scenario: Public lookup of the prescription
    Given the pharmacy needs to validate the prescription
    When the pharmacy accesses the system with the number
    Then it must be possible to check the status and validity of the numbering

  Scenario: Conditional classification field (common prescription)
    Given the user opens the record with a common prescription
    When the system loads the screen
    Then it must show both classification options unchecked
    And require selecting one to proceed

  Scenario: Conditional classification field (special control)
    Given the user opens the record with a special-control prescription
    When the system loads the field
    Then it must show only the applicable option, checked and locked

  Scenario: Selection exclusivity
    Given the user selects one of the options
    When the selection happens
    Then the system automatically unchecks the other option

  Scenario: Block on mandatory field
    Given the user has not selected any mandatory option
    When they try to proceed
    Then the system blocks progress and shows a required-field message

  Scenario: No reuse possible
    Given the pharmacy records the dispensing with the generated number
    When the system receives the information
    Then the number is automatically blocked for future uses
```

## Why this artifact

It demonstrates clear, testable story writing, acceptance criteria in executable format (BDD), handling of conditional behavior and edge cases (mandatory, exclusivity), and attention to compliance rules (anti-reuse).
