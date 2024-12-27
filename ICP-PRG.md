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

|Type|<td colspan=3>Strategy||
|---|---|---|
| Acceptance test | <td colspan=3> Given that the home is mortgaged, when the balance is updated, then the equity in the home should be calculated |
| Component tests | <td colspan=2>Can retrieve mortgage balance | Can retrieve home value estimate |
| Unit tests | Can calculate available equity | Will throw exception on negative equity | Can calculate early payoff amount |