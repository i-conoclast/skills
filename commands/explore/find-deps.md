# Dependency Analysis

Analyzes dependencies of a specific file/module within the codebase.
Identifies internal dependencies, external packages, and reverse dependencies.

## Tasks to Execute

1. Analyze import statements (Grep + Read)
2. Extract internal dependencies (modules within the project)
3. Extract external packages
4. Trace reverse dependencies (where this module is used)
5. Generate dependency graph

## User Input

$ARGUMENTS

- File path: `src/services/auth.py`
- Module name: `src.services.auth`
- Directory: `src/services/`

## Important Notes

- Handle relative imports (from . import ...)
- Detect circular dependencies
- Distinguish stdlib vs 3rd-party for external packages

## Output Format

.claude/templates/explore/find-deps.md format
