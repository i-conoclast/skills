# Change Impact Analysis

Analyzes the scope of impact when modifying a specific file/function.

## Tasks to Execute

1. Identify direct impact using find-usage
2. Build dependency graph using find-deps
3. Calculate indirect impact (A -> B -> C chain)
4. Find related test files
5. Assess risk level

## User Input

$ARGUMENTS

- File path: `src/services/auth.py`
- Function name: `AuthService.validate`
- Class name: `AuthService`

## Important Notes

- Must include test files
- Indirect impact limited to 2-depth only
- Risk level based on number of affected files

## Output Format

.claude/templates/explore/find-impact.md format
