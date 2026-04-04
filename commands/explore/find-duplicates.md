# Detect Duplicate Code

Finds duplicate or similar code within the codebase.

## Tasks to Execute

1. Collect file list
2. Search for similar code patterns (function names, structures)
3. Calculate duplication level (simple heuristics)
4. Suggest extractable common logic

## User Input

$ARGUMENTS

- Directory: `src/services/`
- File pattern: `*.py` or `*.ts`
- Minimum lines: `10` (default)

## Important Notes

- Exclude simple loops/conditionals
- Ignore import statements
- Exclude comments from comparison
- Similarity threshold: 80% or above

## Output Format

.claude/templates/explore/find-duplicates.md format
