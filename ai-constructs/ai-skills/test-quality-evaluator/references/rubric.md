# Test Quality Rubric

Score each dimension from 1 (poor) to 5 (excellent).

## Dimensions

1. Coverage of critical behavior
- Core business flows and high-risk paths are tested.
- Failure and edge cases are tested.

2. Determinism and reliability
- Tests are stable and avoid flaky timing/network dependencies.
- Fixtures and seeds are controlled.

3. Isolation and maintainability
- Unit tests isolate concerns and avoid unnecessary integration coupling.
- Setup/teardown is clear and reusable.

4. Assertion quality
- Assertions verify behavior, not incidental implementation details.
- Negative and invariant assertions exist where needed.

5. Regression protection
- Tests target historically fragile areas and bug-prone logic.
- There are safeguards for bug recurrence.

6. Execution ergonomics
- Test commands are clear and documented.
- Runtime is practical for local and CI usage.

7. CI integration and gates
- Tests run in CI with clear pass/fail reporting.
- Required checks and thresholds are enforced.

## Output Template Guidance

For each model pass include:

1. Overall score (1-5)
2. Table of rubric scores by dimension
3. Top 5 findings with file references
4. Top 5 recommendations, prioritized
