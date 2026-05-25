# QA Testing Project Overview

## Artifacts

- Test Approach & Results (PDF): [https://github.com/sinkinm/testtask/blob/main/Testing%20Approach.pdf]
- Issues (Bug Reports, grouped by severity): [https://github.com/users/sinkinm/projects/1/views/2?visibleFields=%5B%22Title%22%2C351177042%2C%22Labels%22%5D&sortedBy%5Bdirection%5D=desc&sortedBy%5BcolumnId%5D=351177042]
- Functional Checklists: [https://github.com/sinkinm/testtask/blob/main/checklists.md]
- Test Cases (6 structured sample scenarios): [https://github.com/sinkinm/testtask/blob/main/sample_test_cases.md]

---

## Summary

Manual QA assessment of a web-based system focused on core business workflows, UI behavior, and data consistency across.
**Key outcome:** 27 defects found, including 7 critical issues affecting transactional integrity and data correctness.

---

## Quick Metrics

| Metric | Value |
|------|------|
| Total defects | 27 |
| Critical | 7 |
| Major | 15 |
| Minor | 3 |
| Trivial | 2 |

---

## Coverage

- Authentication flow
- Cart and order lifecycle
- Payment workflow (sandbox environment)
- UI components (tables, forms, pagination)
- Data consistency (frontend vs backend)

---

## Testing Approach

- Requirements extracted from `/about` and `/faq` pages due to absence of formal specification
- Atomic decomposition of functional statements into checklist items
- Hybrid execution model: checklist-driven + exploratory testing
- UI validation based on standard industry heuristics (usability, consistency, state correctness)
- Iterative expansion of coverage during execution

---

## Constraints & Assumptions

- API interactions evaluated indirectly via UI due to frontend-controlled request orchestration layer
- Payment flow executed in sandbox/mocked environment without real transaction processing
- Testing limited to observable system behavior within available interface layer

---

## Defect Tracking Model

- GitHub Issues used for individual defect reporting
- GitHub Projects used for classification and grouping by Severity (Blocker / Critical / Major / Minor / Trivial)

---

## Key Observations

- Transactional flows show instability in state consistency and validation logic
- Data integrity issues exist between frontend representation and backend state
- UI layer demonstrates inconsistent handling of edge cases in core components
- Core business flows require stabilization before regression-level testing

---

## Notes

This project demonstrates a structured manual QA approach combining requirement interpretation, checklist-based validation, and exploratory testing. Further iterations should introduce risk-based prioritization and dedicated regression coverage for critical business flows.