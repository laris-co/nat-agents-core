---
description: Initialize minimal ψ/ structure (memory only, no bloat)
allowed-tools:
  - Bash
  - Write
---

# /soul-lite — Lightweight project soul

Setup minimal ψ/ — just memory (retrospectives + learnings).

**Use this for:** Standalone projects, workshops, simple repos.
**Use full `/soul-init` for:** Main workspace with incubate/learn symlinks.

## Step 0: Timestamp (REQUIRED)
```bash
date "+🕐 %H:%M (%A %d %B %Y)"
```

## What This Creates

```
ψ/
├── HOME.md               ← Starting point
├── WIP.md                ← Current work
└── memory/
    ├── retrospectives/   ← Sessions (rrr)
    └── learnings/        ← Patterns found
```

That's it! 5 items, no bloat.

## Steps

### Step 1: Create Structure

```bash
mkdir -p ψ/memory/{retrospectives,learnings}
touch ψ/memory/retrospectives/.gitkeep
touch ψ/memory/learnings/.gitkeep
echo "✅ ψ/ structure created"
```

### Step 2: Create HOME.md

**Write to `ψ/HOME.md`:**

```markdown
# ψ — Project Soul

> "The Oracle Keeps the Human Human"

## Navigation

| Folder | Purpose |
|--------|---------|
| [memory/retrospectives/](memory/retrospectives/) | Session logs (rrr) |
| [memory/learnings/](memory/learnings/) | Patterns & insights |

## Quick Links

- [WIP.md](WIP.md) — Current work

---

*Minimal soul structure. See `/soul-init` for full 5-pillar setup.*
```

### Step 3: Create WIP.md

**Write to `ψ/WIP.md`:**

```markdown
# WIP — Work in Progress

> Last updated: [timestamp]

## Current Focus

- [ ] ...

## Pending

- [ ] ...

---

*Update this file as you work*
```

### Step 4: Update .gitignore (optional)

If project has existing `.gitignore`, append:

```gitignore
# Soul - all tracked (minimal setup)
# No gitignore needed for minimal soul
```

### Step 5: Migrate existing retrospectives (if any)

Check if `retrospectives/` exists at root:

```bash
if [ -d "retrospectives" ] && [ ! -d "ψ/memory/retrospectives" ]; then
  echo "Found retrospectives/ at root"
  echo "Move to ψ/memory/retrospectives/? (manual step)"
fi
```

### Step 6: Confirm

Tell user:
```
✅ Minimal ψ/ created:
   - ψ/HOME.md
   - ψ/WIP.md
   - ψ/memory/retrospectives/
   - ψ/memory/learnings/

Run `rrr` to create your first retrospective!
```

## Comparison

| Feature | soul-lite | soul-init (full) |
|---------|-----------|------------------|
| ψ/memory/ | ✅ | ✅ |
| ψ/active/ | ❌ | ✅ |
| ψ/inbox/ | ❌ | ✅ |
| ψ/writing/ | ❌ | ✅ |
| ψ/lab/ | ❌ | ✅ |
| ψ/incubate/ | ❌ | ✅ |
| ψ/learn/ | ❌ | ✅ |
| .obsidian/ | ❌ | ✅ |
| Best for | Simple projects | Main workspace |

## When to Use

- **soul-lite**: Workshop repo, library, single-purpose project
- **soul-init**: Main brain repo (Nat-s-Agents), needs full pillars
