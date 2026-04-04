# Run Unit Tests

Runs unit tests for quick verification after refactoring or feature modifications.

## Tasks to Execute

1. Identify related tests for changed files or specified modules
2. Run tests (stop on failure)
3. If there are failed tests, analyze the cause and suggest fixes

## User Input

$ARGUMENTS

- No arguments: Run related tests based on recently changed files
- Specify module name: Run only tests related to that module
- File path: Run tests for that file

## Important Notes

- Analyze test results inline without creating files
- On failure, check both code and tests to identify the cause
- Suggest fixes in diff format if modifications are needed

## Output Format

.claude/templates/verify/test-unit.md format
