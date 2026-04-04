# Track Recent Changes

Analyzes recently changed files and content based on git diff.

## Tasks to Execute

1. List changed files with git status
2. Check change details with git diff
3. Classify change types (added/modified/deleted)
4. Summarize key changes

## User Input

$ARGUMENTS

- Range: `HEAD` (default, unstaged changes)
- Commit: `HEAD~1..HEAD` (last commit)
- Branch: `main..feature` (difference between branches)
- Path: `src/` (specific path only)

## Important Notes

- Distinguish between staged and unstaged
- Exclude binary files
- Show only summary for large changes

## Output Format

.claude/templates/explore/find-changes.md format
