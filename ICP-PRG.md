# ICP-PRG

## Unit Tests
Exercises a single piece of code

- Executes quickly
- Independant of other unit tests
- Designed to be used in isolation

A unit tests's small area of focus often makes it simpler to maintain than other types of tests.

## Component Tests
Validates that multiple areas of code work correctly together

- Provides a higher level of confidence about the overall codebase
- Can be more complex to maintain

## Acceptance Tests
Ensures an area of code is following a specified business rule

- Tends to be readable by non-technical team members
- Can be the most complex to maintain

A technically savvy product owner can often author many of the acceptance tests themselves.

## Example

| Type | Strategy |     |     |
| --- | --- | --- | --- |
| Acceptance test | Given that the home is mortgaged, when the balance is updated, then the equity in the home should be calculated |     |     |
| Component tests | Can retrieve mortgage balance | Can retrieve home value estimate |     |
| Unit tests | Can calculate available equity | Will throw exception on negative equity | Can calculate early payoff amount |

## Optimizing Test Coverage

### Right BICEP

- Are the results right?
- Boundary conditions
- Inverse conditions
- Cross-check the results
- Error conditions
- Performance boundaries

### CORRECT

- Conformance
- Ordering
- Range
- Reference
- Existence
- Cardinality
- Time

### Sources of duplication in your test suite

- Multiple tests that validate the same case
- Testing the same area of code with different tests
- Validating the same test case in different ways

Removing duplication across your test suite can improve the overall maintainability of your tests.

### Test-first development

- Tests are written before production code
- Only the code necessary to make tests pass is written
- Tends to results in very lightweight code
- Can lead to duplicated code

### Red, green, refactor

Start with broken tests (red tests), then write just enough code to get them to pass (green tests), and then refactor the code and tests to clean it up.

## Testing your tests

- Write your code using test-first development
- Break your production code and re-run your test suite

### Common indicators of problems with your tests

- Tests do not fail when your production code changes
- The wrong tests fail in response to code changes
- Causes of test failures are not revealed by the test names
- Additional tests fail even though they're unrelated to the changed production code

## Why performance matters

- Long running test suites discourage developers from running tests
- Code committed against a broken test suite is suspect

## Why are yourt tests slow?

- Tests aren't running automatically as part of your build process
- Rely on external dependencies
- Have an inherently high overhead 

## Identifying common test smells

Some of the most challenging smells may only become noticeable over time

- Fragile tests (do not pass consistently)
	- Referencing third party dependencies from your tests often increase the fragility of those tests
- Indirect tests that fail due to changes to unrelated code
- Difficulty adding tests to existing code
	- Production code written in a way that isn't easily testable
- Slow tests

## Improving the performance of your test suite

- Removing external dependencies
	- Code performs faster when entirely in memory
	- Reduces fragility and false negatives
	- Prevents unexpected failures, and improves control over your test suite

### Using test doubles

- Stub
	- Returns hard coded value for the benefit of your test
- Mock
	- Interacts with your production code in predetermined ways
- Fake
	- Replaces an entire external dependency
	- When faking an object, it's not necessary to replace the entire object.  Only fake the methods that your code will be interacting with
- Spy
	- Validates how your production code interacts with an object

## Creating objects using inversion of control

- Often accomplished using dependency injection
- Moves creation of the object outside of the consuming code
- Enables creating the best version of the object at runtime

## Testing code that's inherently hard to test

### Headless apps

Move logic from the UI to areas of the code that can be more readily tested

### Humble objects

Move logic from areas that are difficult to test into areas that are easier to test