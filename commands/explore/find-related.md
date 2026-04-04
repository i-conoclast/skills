# Find Related Files/Tests

Finds other files related to a specific file.

## Tasks to Execute

1. Find files in the same directory/module
2. Search for files with similar name patterns
3. Match related test files (test_*.py, *.test.ts, etc.)
4. Find related documentation files (*.md)

## User Input

$ARGUMENTS

- File path: `src/services/auth.py`
- Test file: `tests/test_auth.py`
- Module: `src.services`

## Important Notes

- Match test files based on naming convention
- Search for .md files with the same name first for documentation
- Exclude __init__.py, index.ts, etc.

## Output Format

.claude/templates/explore/find-related.md format
