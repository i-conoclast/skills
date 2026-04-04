# Write/Update Documentation

Writes or updates documentation.

## Tasks to Execute

1. Identify document type (API docs, design docs, usage guides, etc.)
2. Read existing documentation (if available)
3. Write new content
   - API: endpoints, parameters, responses
   - Design: architecture, decisions
   - Guide: usage instructions, examples
4. Add example code
5. Link related documents

## User Input

$ARGUMENTS

- Document type: "api-spec", "design", "guide", "changelog"
- Target: "Authentication API"
- Option `--update`: Update existing documentation

## Document Format

- Markdown
- Clear heading hierarchy
- Specify language for code blocks
- Include examples

## Output Format

.claude/templates/impl/docs.md format
