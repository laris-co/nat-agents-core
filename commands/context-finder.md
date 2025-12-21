# /context-finder - Search Context

Fast search through git history, retrospectives, issues, and codebase.

## Usage

```
/context-finder [query]
```

## Action

Use the Task tool with subagent_type `context-finder`:

```
subagent_type: context-finder
model: haiku
prompt: |
  Search for context about: $ARGUMENTS

  Run these commands:
  1. git log --oneline --all --grep="$ARGUMENTS" -10
  2. git log --oneline -20 | grep -i "$ARGUMENTS" || true
  3. Find files mentioning the topic
  4. Check retrospectives/ and context/ folders

  Return compact summary of what you found.
```

If no arguments provided, show recent context:
- Last 10 commits
- Recent retrospectives
- Open issues

## Arguments

ARGUMENTS: $ARGUMENTS
