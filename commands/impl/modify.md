# Modify Existing File

Adds or modifies code in an existing file.

## Tasks to Execute

1. Read the target file (Read)
2. Identify modification location
3. Analyze existing patterns (using explore:analyze-code)
4. Modify code (Edit)
5. Update import statements (if needed)
6. Summarize changes

## User Input

$ARGUMENTS

- File path: "src/main.py"
- Modification: "Add new router"
- Option `--at <location>`: Add at a specific line/function

## Modification Rules

- Maintain existing style
- Principle of minimal changes
- Add related imports at the top of the file
- Comment on reason for change (if needed)

## Output Format

.claude/templates/impl/modify.md format
