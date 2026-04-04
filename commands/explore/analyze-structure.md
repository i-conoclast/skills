# Structure Analysis

Analyzes the structure of a directory or module.

## Tasks to Execute

1. File list and statistics (file count, total lines)
2. Visualize directory hierarchy
3. List of key classes/functions (size, complexity)
4. File size distribution analysis

## User Input

$ARGUMENTS

- Directory: `src/services/`
- Module: `src.models`
- Root: `.` (entire project)

## Important Notes

- Exclude caches and build artifacts (__pycache__, node_modules, dist, etc.)
- Count tests/ directory separately

## Output Format

.claude/templates/explore/analyze-structure.md format
