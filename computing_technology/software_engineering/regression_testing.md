<!-- File: computing_technology/software_engineering/regression_testing.md -->

# Regression Testing – Study Notes

## 1. Overview

**Regression testing** is the process of re-running functional and non-functional tests to verify that previously developed and tested software still works correctly after changes. Changes can include:

* Code modifications
* Patches
* Configuration updates
* Any other modifications

---

## 2. Types of Regression Tests

A comprehensive regression test suite typically includes:

1. **Tests focused on changed components**

   * Target the specific software parts that were modified.
   * Ensure that the intended changes work as expected.

2. **Tests focused on existing functionality**

   * Validate that previously working features are not broken.
   * Detect unintended side effects of the changes.

---

## 3. Execution Methods

* **Manual execution**

  * Possible but **not ideal** for frequent or large-scale changes.
  * Time-consuming, error-prone, and costly for repeated runs.

* **Automated execution**

  * Preferred approach for regression testing.
  * Enables fast, repeatable, and consistent testing of all relevant cases.

---

## 4. Scope of Regression Testing

Regression tests may cover:

* **Functional tests:** Verify that software behaves according to specifications.
* **Non-functional tests:** Check performance, security, usability, and other quality attributes.

---

## 5. Key Takeaways

* Regression testing ensures software stability after changes.
* Include tests for both modified and existing functionality.
* Automation is generally preferred, though manual execution is feasible.
* Covers functional **and** non-functional aspects.

---

## 6. Example True/False Evaluation

1. A suite of regression tests should include tests for both changed and existing components → **True**
2. Manual execution of regression tests is unfeasible → **False** (possible but not ideal)
3. Regression tests can involve functional and non-functional tests → **True**

---
