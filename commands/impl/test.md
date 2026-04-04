# Write Tests

Writes test code.

## Tasks to Execute

1. Analyze test target (using explore:analyze-code)
2. Design test cases
   - Normal cases
   - Exception cases
   - Edge cases
3. Create test file
4. Write Fixtures (if needed)
5. Configure Mocks (external dependencies)
6. Run and verify tests

## User Input

$ARGUMENTS

- Target: "src/services/auth.py"
- Option `--unit`: Unit tests only
- Option `--e2e`: E2E tests only
- Option `--all`: Unit + E2E

## Testing Principles

- AAA pattern (Arrange, Act, Assert)
- Each test is independent
- Meaningful test names (test_<action>_<condition>_<result>)
- Fixture reuse

## Output Format

.claude/templates/impl/test.md format
