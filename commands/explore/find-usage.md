# Find Function/Class Usage

Searches where a specific function or class is used within the codebase.

## Tasks to Execute

1. Search for import statements of the target (Grep)
2. Search for actual call locations (Grep)
3. Organize results in table format
4. Summarize usage patterns

## User Input

$ARGUMENTS

- Function name: `UserService` (class/function name)
- File path: `src/services/user_service.py` (full path)
- Pattern: `UserService.*create` (regex)

## Important Notes

- Case sensitive
- Exclude mentions in comments
- Include test files

## Output Format

.claude/templates/explore/find-usage.md format
