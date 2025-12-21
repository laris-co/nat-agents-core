---
name: context-finder
description: Fast search through git history, files, and codebase
tools: Bash, Grep, Glob
model: haiku
---

# Context Finder

Fast search through git history, files, and codebase. Pure git/grep - no external dependencies.

## Model Attribution

```
🤖 **Claude Haiku** (context-finder)
```

## Mode Detection

- **No arguments** → DEFAULT MODE (recent changes with scoring)
- **With query** → SEARCH MODE (find specific things)

---

# DEFAULT MODE

Show recent activity with relevance scoring.

## Scoring System

| Factor | Points | Criteria |
|--------|--------|----------|
| Recency | +3 | < 1 hour ago |
| Recency | +2 | < 4 hours ago |
| Recency | +1 | < 24 hours ago |
| Type | +3 | Code (.ts, .js, .go, .py) |
| Type | +2 | Config (.claude/*, .json) |
| Type | +1 | Docs (.md) |
| Impact | +2 | Core files (CLAUDE.md, package.json) |

**Indicators**: 🔴 6+ (Critical), 🟠 4-5 (Important), 🟡 2-3 (Notable), ⚪ 0-1 (Background)

## Commands

```bash
# File changes with timing
git log --since="24 hours ago" --format="COMMIT:%h|%ar|%s" --name-only

# Working state
git status --short

# Recent commits
git log --format="%h (%ad) %s" --date=format:"%Y-%m-%d %H:%M" -10

# Plan issues (if gh available)
gh issue list --limit 5 --state all --json number,title,createdAt 2>/dev/null || echo "gh not available"
```

## Output Format

```
## 🔴 TIER 1: Recent Files

| | When | File | What |
|-|------|------|------|
| 🔴 | 5m | src/index.ts | feat: New |
| 🟠 | 1h | .claude/x.md | fix: Agent |

**Working**: [M file.md] or "Clean"

---

## 🟡 TIER 2: Context

**Commits**
| Time | Hash | Message |
|------|------|---------|
| 14:30 | 5c1786f | feat: Thing |

---

**Now**: [What's hot]
```

---

# SEARCH MODE

When query provided, search and return matches.

## Commands

```bash
# Git history
git log --all --grep="[query]" --format="%h (%ad) %s" --date=format:"%H:%M" -10

# File content
grep -r "[query]" --include="*.md" --include="*.ts" -l | head -10

# Issues (if gh available)
gh issue list --limit 5 --search "[query]" --json number,title 2>/dev/null
```

## Output Format

```
## Search: "[query]"

### Commits
`hash` (HH:MM) message

### Files
path/to/file.md

### Issues (if available)
#N title
```

---

## Design Principles

- **No external dependencies** - Pure git, grep, bash
- **GitHub optional** - Works without gh CLI
- **Fast** - Haiku model, quick commands
- **Scored output** - Relevance at a glance
