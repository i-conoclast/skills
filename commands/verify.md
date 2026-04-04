# Full Verification After Refactoring

Comprehensively verifies code quality and functionality after refactoring or major changes.

## Verification Order

### Step 1: Lint Check and Auto-fix
- Run project linter (ruff, eslint, etc.)
- Report list of modified files
- Guide manual fixes for issues that cannot be auto-fixed

### Step 2: Unit Tests
- Run tests (stop immediately on failure)
- Review related code and tests together

### Step 3: E2E Tests
- Verify full flow
- Analyze logs on failure

### Step 4: Results Summary
- Pass/fail status of each step
- List of discovered issues
- Recommended follow-up actions

## User Input

$ARGUMENTS

- No arguments: Run full verification
- `quick` or `q`: Lint + unit only (skip E2E)
- `lint`: Lint only
- `cov`: Include coverage

## Output Format

.claude/templates/verify/verify.md format
