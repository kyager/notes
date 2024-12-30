## ICP-PRG

### Unit Tests
Exercises a single piece of code

- Executes quickly
- Independant of other unit tests
- Designed to be used in isolation

A unit tests's small area of focus often makes it simpler to maintain than other types of tests.

### Component Tests
Validates that multiple areas of code work correctly together

- Provides a higher level of confidence about the overall codebase
- Can be more complex to maintain

### Acceptance Tests
Ensures an area of code is following a specified business rule

- Tends to be readable by non-technical team members
- Can be the most complex to maintain

A technically savvy product owner can often author many of the acceptance tests themselves.

### Example

| Type | Strategy |     |     |
| --- | --- | --- | --- |
| Acceptance test | Given that the home is mortgaged, when the balance is updated, then the equity in the home should be calculated |     |     |
| Component tests | Can retrieve mortgage balance | Can retrieve home value estimate |     |
| Unit tests | Can calculate available equity | Will throw exception on negative equity | Can calculate early payoff amount |

# Optimizing Test Coverage

## Right BICEP

- Are the results right?
- Boundary conditions
- Inverse conditions
- Cross-check the results
- Error conditions
- Performance boundaries

## CORRECT

- Conformance
- Ordering
- Range
- Reference
- Existence
- Cardinality
- Time

## Sources of duplication in your test suite

- Multiple tests that validate the same case
- Testing the same area of code with different tests
- Validating the same test case in different ways

Removing duplication across your test suite can improve the overall maintainability of your tests.

## Test-first development

- Tests are written before production code
- Only the code necessary to make tests pass is written
- Tends to results in very lightweight code
- Can lead to duplicated code

## Red, green, refactor

Start with broken tests (red tests), then write just enough code to get them to pass (green tests), and then refactor the code and tests to clean it up.

# Testing your tests